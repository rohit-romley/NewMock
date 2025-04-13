# Product Requirements Document: Mockaccino Mobile App



**Version:** 1.0

**Date:** April 12, 2025

**Author(s):** Gemini

**Stakeholders:** Product Management, Engineering Team, Design Team, Marketing Team



## 1. Overview & Goals



* **Introduction:** Mockaccino is a mobile application designed to connect professionals seeking to practice interview skills and exchange job referrals. It facilitates networking by allowing users to match based on their current roles, target roles, and desired interaction (mock interview or referral exchange).

* **Problem Statement:** Job seekers, particularly those transitioning careers or new to the workforce, often lack accessible, relevant opportunities for mock interviews and struggle to build a network for potential job referrals. Existing professional networking platforms may not specifically cater to these needs in a focused, user-friendly way.

* **Target Audience:** Professionals actively seeking jobs, individuals looking to switch careers, recent graduates entering the job market, anyone wanting to improve their interviewing skills, and users aiming to expand their professional network for referral opportunities.

* **Value Proposition:** Mockaccino offers a dedicated, mobile-first platform for users to easily find and connect with peers for targeted mock interviews and referral exchanges, thereby enhancing their job search preparedness and networking reach. It provides both free core functionality and optional premium features.

* **Goals/Objectives:**

    * Launch MVP on iOS and Android platforms by Q4 2025.

    * Acquire 10,000 registered users within 6 months post-launch.

    * Achieve an average of 1,000 daily active users (DAU) within 6 months post-launch.

    * Facilitate 20,000 matches resulting in conversations within the first year.

    * Achieve a 5% conversion rate to the Premium subscription within the first year.

* **Success Metrics:**

    * Number of Registered Users

    * Daily Active Users (DAU) / Monthly Active Users (MAU)

    * Number of Swipes (Right/Left) per User Session

    * Match Rate (Mutual Likes / Total Right Swipes)

    * Conversation Rate (Messages Sent / Matches Made)

    * Premium Subscription Conversion Rate

    * App Store Ratings & Reviews

    * User Retention Rate

    * Task Completion Rate (e.g., Profile Setup, First Message Sent)



## 2. Core Features & Requirements



* **Feature 1: User Authentication & Profile Management**

    * **Description:** Enables users to securely create accounts, log in, and manage their professional profiles.

    * **Functional Requirements:**

        * 1.1: As a new user, I want to sign up using my Email address, Apple ID, or LinkedIn account, so that I can create an account easily. (See Pages 4, 5)

        * 1.2: As a new user, I must provide my Full Name, Email, City, and Password, and optionally upload a Profile Picture during email sign-up. (See Page 5)

        * 1.3: As a new user, I must accept the Terms of Service and Privacy Policy to complete sign-up. (See Page 5)

        * 1.4: As an existing user, I want to log in using my Email/Password, Apple ID, or LinkedIn account. (See Page 4)

        * 1.5: As a user who forgot their password, I want a way to reset it. (See Page 4)

        * 1.6: As a new user, I want to select my Current Role and Target Role during onboarding to help find relevant matches. (See Pages 6, 7)

        * 1.7: As a new user, I want to specify if I'm interested in Referral Exchange, Mock Interviews, or Both during onboarding. (See Page 8)

        * 1.8: As a user, I want my profile to display my Photo, Name, Age (optional/derived), Location, Current Role, Target Role, Bio, Interaction Preference (Mock Interview/Referral Exchange), Skills, and Availability Schedule. (See Pages 9, 14, 19)

        * 1.9: As a user, I want to be able to edit all aspects of my profile after creation. (See Page 21)

        * 1.10: As a user, I want to be able to log out of my account. (See Page 15)

        * 1.11: As a user, I want the option to deactivate my account. (See Page 15)

    * **High-Level Workflow:** User launches app -> Selects Sign Up/Login -> Provides credentials or uses SSO -> (New User) Completes profile setup (Roles, Preferences) -> Lands on main matching screen. (Existing User) Lands on main matching screen. User can navigate to profile/settings to view/edit details.



* **Feature 2: Matching & Discovery**

    * **Description:** Allows users to discover potential connections through a card-swiping interface and indicates mutual interest.

    * **Functional Requirements:**

        * 2.1: As a user, I want to see potential matches presented as profile cards, one at a time. (See Pages 9, 10)

        * 2.2: As a user, I want to swipe right on a profile card to indicate interest (like) or swipe left to pass. (Implied by swipe-based UI)

        * 2.3: As a user, I want profile cards to display key information: Photo, Name, Age, Roles, Location, Interaction Preference, Bio snippet. (See Pages 9, 10)

        * 2.4: As a user, I want to be notified with an "It's a Match!" screen when mutual interest occurs (both users swipe right). (See Page 17)

        * 2.5: As a user on the free tier, I want to understand that I have a limited number of right swipes per day/period. (See Page 24)

        * 2.6: As a user who runs out of likes, I want to see a screen informing me and prompting me to wait or upgrade. (See Page 24)

    * **High-Level Workflow:** User views profile card on the main screen -> Swipes left or right -> The next card is presented -> If a mutual right swipe occurs, the match screen is displayed, offering options to message or continue swiping.



* **Feature 3: Chat**

    * **Description:** Enables real-time text communication between matched users.

    * **Functional Requirements:**

        * 3.1: As a user, I want a dedicated "Chats" tab listing all my ongoing conversations with matches. (See Page 11)

        * 3.2: As a user, I want the chat list to show the match's name, last message preview, timestamp, and unread message count. (See Page 11)

        * 3.3: As a user, I want to tap on a conversation in the list to open the chat screen.

        * 3.4: As a user, I want a chat interface displaying messages chronologically, sender identification, timestamps, and an input field to type and send messages. (See Page 20)

        * 3.5: As a user, I want to receive notifications (in-app and potentially push) for new messages. (See Page 16)

    * **High-Level Workflow:** User receives a match -> Navigates to the "Chats" tab or taps "Send a Message" -> Selects the matched user -> Types and sends messages in the chat interface.



* **Feature 4: Premium Features & Subscription**

    * **Description:** Offers enhanced functionality through a paid subscription model.

    * **Functional Requirements:**

        * 4.1: As a Premium user, I want to have unlimited right swipes. (See Page 23)

        * 4.2: As a Premium user, I want to access a "Likes" tab to see a list of users who have swiped right on my profile. (See Pages 12, 13, 23)

        * 4.3: As a Premium user, I want to apply filters to my potential matches based on Role, Interview Preference, Search Distance, and City. (See Pages 18, 23)

        * 4.4: As a free user, I want to see prompts to upgrade to Premium when accessing premium features (like the "Likes" tab or filters) or when running out of likes. (See Pages 13, 24)

        * 4.5: As a user, I want a dedicated screen clearly outlining the benefits and cost ($3.99/mo) of the Premium subscription. (See Page 23)

        * 4.6: As a user, I want to be able to securely purchase the Premium subscription using standard payment methods (Visa, Mastercard, PayPal indicated). (See Page 22)

    * **High-Level Workflow:** User encounters a premium feature prompt or navigates to the Premium screen -> Reviews benefits and cost -> Proceeds to payment -> Enters payment details securely -> Completes purchase -> Account is upgraded, and premium features are unlocked.



* **Feature 5: Settings & Notifications**

    * **Description:** Provides users control over their account, preferences, and notifications.

    * **Functional Requirements:**

        * 5.1: As a user, I want a Settings screen to manage my account. (See Page 15)

        * 5.2: As a user, I want options to control Account Visibility (details TBD) and Notification preferences. (See Page 15)

        * 5.3: As a user, I want to be able to change my account password. (See Page 15)

        * 5.4: As a user, I want to view my unique Invite Code (functionality TBD). (See Page 15)

        * 5.5: As a user, I want access to legal documents (Privacy Policy, Terms of Service, Licenses). (See Page 15)

        * 5.6: As a user, I want to view the app version number. (See Page 15)

        * 5.7: As a user, I want a notification center listing recent activity like new matches and messages. (See Page 16)

    * **High-Level Workflow:** User navigates to the Settings screen -> Modifies options like notifications or password -> Changes are saved. User navigates to the Notifications screen -> Views recent activity.



## 3. User Experience (UX) & Design



* **User Journey Map(s):**

    * *Onboarding:* App Install -> Sign Up (Email/SSO) -> Accept ToS -> Select Current Role -> Select Target Role -> Select Interaction Preference -> View Main Matching Screen.

    * *Finding a Match:* View Profile Card -> Swipe Right -> View Next Card -> Receive "It's a Match!" notification.

    * *Starting Conversation:* Receive Match -> Tap "Send a Message" or Go to Chats Tab -> Select Match -> Type & Send Message.

    * *Upgrading:* Hit Like Limit / Tap "Likes" Tab -> View Premium Screen -> Tap "Get Premium" -> Enter Payment Info -> Complete Purchase.

* **Wireframes/Mockups:** The provided PDF document serves as high-fidelity mockups for the application's UI.

* **UI/UX Considerations:**

    * Maintain a clean, intuitive, and modern mobile interface.

    * Ensure the swiping gesture is smooth and responsive.

    * Use clear typography and sufficient color contrast for readability (WCAG AA compliance target).

    * Consistent use of branding elements (logo, color scheme: white, black, blues, orange accent).

    * Follow platform-specific (iOS/Android) navigation and UI conventions.

    * Provide clear visual feedback for user actions (e.g., button presses, successful swipes).



## 4. Technical Architecture & Implementation



* **System Overview:** A mobile application (potentially cross-platform using React Native or Flutter) communicating with a backend API service, utilizing a cloud database and real-time communication features.

* **Components:**

    * **Mobile Client:** iOS/Android application.

    * **Backend API:** RESTful API (e.g., built with Node.js/Express or Python/Flask) hosted on a serverless platform.

    * **Database:** NoSQL database (e.g., Firestore) for storing user profiles, matches, chats.

    * **Real-time Service:** Utilize database listeners (e.g., Firestore listeners) or WebSockets for chat functionality.

    * **Push Notifications:** Firebase Cloud Messaging (FCM) for Android, Apple Push Notification Service (APNS) for iOS.

    * **Image Storage:** User profile pictures stored in cloud storage. **Firebase Storage** is recommended for integration; **ImgBB** can be used as an alternative if required, but will necessitate separate API calls.

* **Data Models (High-Level):**

    * `UserProfile`: userId, name, email (hashed/secured), authProvider, city, profilePicUrl, currentRole, targetRole, interactionPreference, bio, skills[], availabilitySchedule, isPremium, premiumExpiry, creationDate, lastLogin, etc.

    * `Swipe`: swiperUserId, swipedUserId, direction (like/pass), timestamp.

    * `Match`: matchId, userIds[2], timestamp.

    * `ChatMessage`: messageId, matchId, senderUserId, text, timestamp, readStatus.

    * `Notification`: notificationId, userId, type (match/message), relatedUserId, messageSnippet, timestamp, readStatus.

* **APIs & Integrations:**

    * Internal Backend API (for client use).

    * Authentication: Firebase Authentication (Email, Apple, LinkedIn providers).

    * Payment Gateway: Integration with a provider like Stripe or Braintree for handling subscriptions (requires secure handling).

    * Push Notifications: FCM/APNS.

    * Image Hosting: Firebase Storage API or ImgBB API.

* **Infrastructure Requirements:**

    * **Hosting:** **Firebase Hosting** for web assets (if any) and **Firebase Cloud Functions** or similar serverless platform for the backend API. These services offer generous free tiers suitable for MVP and initial scaling.

    * **Database:** **Firebase Firestore** (NoSQL, real-time capabilities, generous free tier).

    * **Authentication:** **Firebase Authentication** (free tier supports sufficient users for launch).

    * **Storage:** **Firebase Storage** for user images (free tier available). Alternatively, **ImgBB** (free image hosting, requires managing API keys and integration).

* **Non-Functional Requirements:**

    * **Performance:** Profile loading < 2 seconds. Swipe animations > 30 FPS. Real-time chat message delivery < 1 second under normal conditions.

    * **Security:** HTTPS for all communication. Secure storage of credentials/tokens. Input validation. Protection against common mobile app vulnerabilities. Secure payment processing (PCI DSS compliance via gateway).

    * **Scalability:** Utilize cloud-based, auto-scaling services (Firebase services are designed for this).

    * **Maintainability:** Code commenting, modular design, version control, automated testing (unit/integration).

    * **Reliability:** Target 99.5% uptime for backend services. Graceful handling of network errors on the client.



## 5. Phased Development & Release Plan



* **Development Phasing Strategy:** Agile, iterative development. Focus on delivering the core value proposition (match & chat) in the MVP, followed by enhancements and premium features.

* **Phase 1: Minimum Viable Product (MVP)**

    * **Scope:** Feature 1 (Email Auth, Profile Create/View/Edit), Feature 2 (Basic Swiping & Matching logic, Limited Likes), Feature 3 (Core Chat), Feature 5 (Basic Settings - Logout, Legal Links, View Profile). No Premium features, no advanced filtering, no SSO login initially.

    * **Rationale:** Provides the essential functionality for users to connect and communicate, validating the core concept and gathering initial user feedback.

* **Phase 2: Post-MVP Enhancements**

    * **Scope:** Implement remaining Auth options (Apple, LinkedIn), Forgot Password flow, Premium Subscription (Feature 4 - Unlimited Likes, See Likes, Basic Filters), Push Notifications, Invite Code display (backend logic TBD), Notification Screen population.

* **Future Phases/Enhancements:**

    * **Scope:** Advanced Filtering options, Availability Schedule integration/filtering, In-app Scheduling tools, Profile Verification, Enhanced Matching Algorithms, User Reporting/Blocking, Admin Moderation Tools, In-app Video Call support for mock interviews.

* **Release Criteria (MVP):**

    * All MVP scope features implemented and tested.

    * Core user flow (Sign up -> Profile -> Swipe -> Match -> Chat) is stable.

    * No critical or blocker bugs.

    * App successfully builds and runs on target iOS/Android versions.

    * Basic security checks passed.

    * Privacy Policy and Terms of Service are finalized and linked.

    * Deployment pipeline to App Store / Google Play is functional.



## 6. Risks & Mitigations



| Risk Category   | Specific Risk Description                                     | Likelihood | Impact | Mitigation Plan                                                                                                |

| :-------------- | :------------------------------------------------------------ | :--------- | :----- | :------------------------------------------------------------------------------------------------------------- |

| Technical       | Real-time chat scaling issues under heavy load.               | Med        | High   | Use scalable backend (Firestore), optimize data structures, load test simulated scenarios.                        |

| Technical       | Securely integrating third-party payment gateway.             | Med        | High   | Use reputable providers (Stripe/Braintree), follow documentation closely, perform security audits, allocate testing time. |

| Resource        | Limited developer resources slowing down feature development. | Med        | Med    | Prioritize features ruthlessly (focus on MVP), consider cross-platform frameworks, clear task definition.        |

| Scope           | Scope creep delaying MVP launch.                              | High       | High   | Strict adherence to MVP scope definition, regular backlog grooming, stakeholder communication on trade-offs. |

| Definition      | MVP lacks sufficient value to retain early adopters.          | Med        | High   | User testing of core loop prototype, focus on quality/usability of MVP features, gather feedback early.        |

| Adoption        | Difficulty attracting a critical mass of users for matching.  | High       | High   | Pre-launch marketing, target niche communities (universities, bootcamps), implement referral/invite system early. |

| Monetization    | Low Premium conversion rate impacts revenue goals.            | Med        | Med    | Ensure Premium features offer clear value, A/B test pricing/promotions, gather user feedback on perceived value. |

| Platform Policy | App rejection due to perceived similarity to dating apps.    | Low        | High   | Clearly position app for professional networking, emphasize mock interviews/referrals, carefully review store guidelines. |



## 7. Out of Scope / Future Considerations



* In-app video calling capabilities.

* Direct calendar integration or scheduling tools.

* Advanced profile verification badges.

* Group features or forums.

* Web-based version of the application.

* Gamification elements (points, badges).

* Integration with job boards.

* Advanced analytics dashboard for users.



## 8. Open Issues & Questions



* What is the specific algorithm for presenting potential matches in the MVP? (Initial: Target Role = Current Role, Interaction Preference match, basic location proximity?)

* Detailed requirements for the "Account Visibility" setting? (e.g., Hide profile temporarily, Incognito mode?)

* How will the Invite Code system function? (e.g., Rewards for inviter/invitee, tracking?)

* Is user age required or optional? How is it captured/displayed?

* What is the initial strategy for content moderation and handling user reports?

* Specific list of selectable "Skills"?

* Detailed requirements for the "Availability Schedule" format and potential filtering?