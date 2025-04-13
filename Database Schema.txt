# Mockaccino Firestore Database Schema (v1.0)

This document outlines a suggested NoSQL database structure for the Mockaccino mobile application, designed for use with Google Cloud Firestore.

---

## Collection: `users`

**Description:** Stores individual user profile information, authentication details, preferences, and application-specific status. The Document ID for each document should be the unique User ID (`userId`) provided by the authentication system (e.g., Firebase Auth UID).

| FieldName                 | DataType                   | Description                                                                 | Required      |
| :------------------------ | :------------------------- | :-------------------------------------------------------------------------- | :------------ |
| `userId`                  | String                     | Unique identifier for the user (matches Auth UID, used as Document ID).     | Yes           |
| `email`                   | String                     | User's primary email address.                                               | Yes           |
| `fullName`                | String                     | User's full name.                                                           | Yes           |
| `authProvider`            | String                     | Method used for signup/login ('email', 'apple.com', 'linkedin.com').        | Yes           |
| `city`                    | String                     | User's primary city for location context.                                   | Yes           |
| `location`                | GeoPoint                   | User's precise location (latitude/longitude) for distance-based filtering.  | No (Optional) |
| `profilePictureUrl`       | String                     | URL of the user's profile picture (hosted on Cloud Storage/ImgBB).          | No (Optional) |
| `currentRole`             | String                     | User's current job title or role.                                           | Yes           |
| `targetRole`              | String                     | User's desired job title or role for matching.                              | Yes           |
| `interactionPreference`   | String                     | User's goal ('Mock Interview', 'Referral Exchange', 'Both').                | Yes           |
| `bio`                     | String                     | Short user biography or description.                                        | No (Optional) |
| `skills`                  | Array<String>              | List of professional skills.                                                | No (Optional) |
| `availabilitySchedule`    | Map<String, Array<String>> | User's general availability (e.g., `{"monday": ["afternoon", "evening"]}`). | No (Optional) |
| `isPremium`               | Boolean                    | Flag indicating if the user has an active premium subscription.             | Yes (Default: false) |
| `premiumExpiryDate`       | Timestamp                  | Expiration date of the current premium subscription (if `isPremium` is true). | Conditional   |
| `accountStatus`           | String                     | Current status of the account ('active', 'deactivated').                    | Yes (Default: 'active') |
| `notificationPreferences` | Map<String, Boolean>       | User settings for different notification types (e.g., `{"newMatch": true}`). | No (Default map) |
| `deviceTokens`            | Array<String>              | List of push notification tokens for the user's devices (FCM/APNS).         | No (Optional) |
| `dailySwipeCount`         | Number                     | Number of right swipes made today (for free tier limits).                   | Yes (Default: 0) |
| `lastSwipeResetTimestamp` | Timestamp                  | Timestamp when the daily swipe limit was last reset.                        | Yes           |
| `inviteCode`              | String                     | Unique code assigned to the user for inviting others (functionality TBD).   | No (Generated later) |
| `createdAt`               | Timestamp                  | Timestamp when the user account was created.                                | Yes           |
| `lastLoginAt`             | Timestamp                  | Timestamp of the user's last login.                                         | Yes           |

**Relationships:**
* This is the central collection. Document IDs (`userId`) are referenced in `swipes`, `matches`, `messages`, `notifications`, and `subscriptions`.

**Potential Indexes:**
* `city` (for filtering by city)
* `location` (for geospatial queries, e.g., finding users within X distance)
* `currentRole` (for filtering)
* `targetRole` (for filtering)
* `interactionPreference` (for filtering)
* `isPremium` (for segmenting users)
* `lastLoginAt` (for user activity tracking/cleanup)
* Composite: (`targetRole`, `interactionPreference`, `location`) - For core matching logic based on premium filters.
* Composite: (`currentRole`, `interactionPreference`, `location`) - Alternative matching logic.

---

## Collection: `swipes`

**Description:** Records each swipe action (like or pass) performed by a user on another user's profile. Used to determine matches and populate the "Who Liked Me" feature for premium users.

| FieldName      | DataType  | Description                                                    | Required |
| :------------- | :-------- | :------------------------------------------------------------- | :------- |
| `swiperUserId` | String    | The `userId` of the user who performed the swipe.              | Yes      |
| `swipedUserId` | String    | The `userId` of the user whose profile was swiped.             | Yes      |
| `direction`    | String    | The direction of the swipe ('like' or 'pass').                 | Yes      |
| `timestamp`    | Timestamp | Timestamp when the swipe action occurred.                      | Yes      |

**Relationships:**
* References `users` collection via `swiperUserId` and `swipedUserId`.

**Potential Indexes:**
* Composite: (`swipedUserId`, `direction`, `timestamp`) - Crucial for efficiently querying "Who Liked Me" (`direction == 'like'`). Order by `timestamp` DESC.
* Composite: (`swiperUserId`, `timestamp`) - For querying a user's own swipe history or potentially enforcing swipe limits if not handled in the `users` doc.
* Composite: (`swiperUserId`, `swipedUserId`) - To quickly check if a swipe already exists between two users.

---

## Collection: `matches`

**Description:** Represents a mutual 'like' between two users. This collection also serves as the container for chat metadata and the associated messages subcollection. Document ID could be auto-generated or a composite key (e.g., `userId1_userId2` sorted alphabetically).

| FieldName             | DataType             | Description                                                                                                   | Required    |
| :-------------------- | :------------------- | :------------------------------------------------------------------------------------------------------------ | :---------- |
| `matchId`             | String               | Unique identifier for the match (used as Document ID).                                                        | Yes         |
| `userIds`             | Array<String>        | An array containing the two `userId`s of the matched users.                                                   | Yes (Size: 2) |
| `createdAt`           | Timestamp            | Timestamp when the match occurred (mutual like).                                                              | Yes         |
| `participantInfo`     | Map<String, Map>     | Denormalized user info for quick display in chat lists. ` { "userId1": {"name": "...", "photoUrl": "..."}, ...}` | Yes         |
| `lastMessagePreview`  | String               | Denormalized text snippet of the most recent message in the chat.                                             | No          |
| `lastMessageTimestamp`| Timestamp            | Denormalized timestamp of the most recent message. Used for sorting chat lists.                               | No          |
| `unreadCounts`        | Map<String, Number>  | Denormalized count of unread messages per user. ` { "userId1": 0, "userId2": 2 }`                             | Yes (Default: {userId1:0, userId2:0}) |
| `status`              | String               | Status of the match/chat (e.g., 'active', 'unmatched', 'blocked').                                            | Yes (Default: 'active') |

**Subcollection:** `messages`

**Relationships:**
* References `users` via the `userIds` array and `participantInfo` map keys.
* Contains the `messages` subcollection.
* Denormalizes `fullName` and `profilePictureUrl` from `users` into `participantInfo`.
* Denormalizes data (`lastMessagePreview`, `lastMessageTimestamp`, `unreadCounts`) from the `messages` subcollection for performance.

**Potential Indexes:**
* `userIds` (`array-contains`) - Essential for finding all matches for a specific user.
* Composite: (`userIds` `array-contains`, `lastMessageTimestamp`) - For querying a user's matches sorted by recent activity.

---

### Subcollection: `matches/{matchId}/messages`

**Description:** Stores individual chat messages exchanged between two matched users. Each document represents one message. Resides within a specific `matches` document.

| FieldName      | DataType  | Description                                                     | Required |
| :------------- | :-------- | :-------------------------------------------------------------- | :------- |
| `messageId`    | String    | Unique identifier for the message (used as Document ID).        | Yes      |
| `senderUserId` | String    | The `userId` of the user who sent the message.                  | Yes      |
| `text`         | String    | The content of the chat message.                                | Yes      |
| `timestamp`    | Timestamp | Timestamp when the message was sent.                            | Yes      |
| `readStatus`   | Map<String, Boolean> | Tracks if each participant has read the message. `{ "userId1": true, "userId2": false }` | Yes (Default: sender=true, other=false) |


**Relationships:**
* Belongs to a parent document in the `matches` collection.
* References `users` via `senderUserId`.

**Potential Indexes:**
* `timestamp` (ASC or DESC) - Essential for fetching messages in chronological order for the chat screen.

---

## Collection: `notifications`

**Description:** Stores in-app notifications for users, such as new matches or new messages.

| FieldName         | DataType  | Description                                                                    | Required    |
| :---------------- | :-------- | :----------------------------------------------------------------------------- | :---------- |
| `notificationId`  | String    | Unique identifier for the notification (used as Document ID).                  | Yes         |
| `recipientUserId` | String    | The `userId` of the user who should receive this notification.                 | Yes         |
| `type`            | String    | Type of notification ('new_match', 'new_message', 'premium_reminder', etc.).   | Yes         |
| `title`           | String    | Short title for the notification display.                                      | Yes         |
| `body`            | String    | Main content/message of the notification. Includes sender name/message snippet. | Yes         |
| `senderUserId`    | String    | The `userId` of the user triggering the notification (e.g., message sender).   | Conditional |
| `relatedMatchId`  | String    | The `matchId` related to this notification (if applicable).                    | Conditional |
| `isRead`          | Boolean   | Flag indicating if the user has read the notification.                         | Yes (Default: false) |
| `createdAt`       | Timestamp | Timestamp when the notification was generated.                                 | Yes         |

**Relationships:**
* References `users` via `recipientUserId` and potentially `senderUserId`.
* References `matches` via `relatedMatchId` (for navigating to the relevant match/chat).

**Potential Indexes:**
* Composite: (`recipientUserId`, `createdAt`) - To fetch notifications for a user, sorted by time (DESC).
* Composite: (`recipientUserId`, `isRead`, `createdAt`) - To fetch unread notifications for a user.

---

## Collection: `subscriptions`

**Description:** Tracks user subscription purchase history and status, primarily for record-keeping and potential customer support.

| FieldName            | DataType  | Description                                                              | Required    |
| :------------------- | :-------- | :----------------------------------------------------------------------- | :---------- |
| `subscriptionId`     | String    | Unique identifier for the subscription record (used as Document ID).     | Yes         |
| `userId`             | String    | The `userId` associated with this subscription purchase.                 | Yes         |
| `productId`          | String    | Identifier for the purchased product (e.g., 'mockaccino_premium_monthly'). | Yes         |
| `purchaseDate`       | Timestamp | Timestamp when the subscription was purchased or renewed.                | Yes         |
| `expiryDate`         | Timestamp | Timestamp when the subscription access expires.                          | Yes         |
| `status`             | String    | Current status ('active', 'cancelled', 'expired', 'payment_failed').     | Yes         |
| `paymentGateway`     | String    | Name of the payment provider used (e.g., 'Stripe', 'Braintree', 'GooglePlay', 'AppStore'). | Yes         |
| `gatewayTransactionId`| String    | Transaction ID from the payment gateway for reference.                   | Conditional |
| `createdAt`          | Timestamp | Timestamp when this subscription record was created.                     | Yes         |

**Relationships:**
* References `users` via `userId`.

**Potential Indexes:**
* `userId` - To query subscription history for a specific user.
* Composite: (`userId`, `expiryDate`) - To check active subscriptions for a user.
* Composite: (`userId`, `status`) - To find subscriptions with a specific status for a user.
* `expiryDate` - Potentially for background jobs checking for expired subscriptions.

---

## Summary of Relationships & Denormalization

* **User ID (`userId`)** is the primary key linking most collections.
* **Denormalization:**
    * `matches`: Contains `participantInfo` (name, photoUrl), `lastMessagePreview`, `lastMessageTimestamp`, and `unreadCounts`. This significantly speeds up loading the main chat list screen by avoiding extra reads to `users` and `messages` subcollections for every match displayed.
    * **Tradeoff:** Requires updating the `matches` document whenever participant profile info changes (less frequent) or when a new message is sent (more frequent). This adds write complexity but improves read performance for a common use case. Use Cloud Functions triggers to manage these updates reliably.

This structure provides a solid foundation for Mockaccino. Remember that NoSQL schema design is often iterative; you may refine this further based on specific query patterns, performance testing, and evolving feature requirements.
