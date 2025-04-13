# Mockaccino Mobile App - Screen Flows v1.0

Based on PRD v1.0 and User Stories v1.0.

---

## Flow: New User Onboarding & Sign Up (Email Primary)

* **Goal:** A new user creates an account using their email and completes the initial profile setup.
* **References:** PRD Sec 2 (Feature 1), PRD Sec 3 (Journey Map), User Stories F1.1, F1.2, F1.3, F1.6, F1.7.

1.  **Screen:** Initial App Launch / Landing Screen (PRD Page 4)
    * **Info:** Displays options: "Sign Up with Email", "Log In", and potentially "Sign Up with Apple", "Sign Up with LinkedIn" (Post-MVP, F1.12, F1.13).
    * **Action:** User taps "Sign Up with Email" button.
    * **-> Transition:** Navigate to Email Sign Up Screen.

2.  **Screen:** Email Sign Up Screen (PRD Page 5)
    * **Info:** Fields for Full Name, Email, City, Password, Confirm Password, Profile Picture upload (optional), Checkbox for Terms acceptance.
    * **Action:** User enters valid Full Name, unique Email, City, strong Password, confirms password.
    * **-> State Change:** Input fields show entered data.
    * **Action (Optional):** User taps profile picture placeholder -> Selects image from camera/gallery -> Image uploads and displays. (F1.2)
    * **Action:** User taps "Terms of Service" or "Privacy Policy" links.
    * **-> Transition:** Display respective legal documents (e.g., in-app view). User returns to sign-up screen.
    * **Action:** User checks the "I accept the Terms of Service and Privacy Policy" checkbox. (F1.3)
    * **-> State Change:** 'Sign Up' button becomes enabled (assuming all required fields are valid).
    * **Action:** User taps 'Sign Up' button.
    * **-> System Event:** Backend validates data (unique email, password match, etc.).
    * **-> Transition (Success):** Account created. Navigate to Select Current Role Screen.
    * **-> Transition (Failure):** Display specific error message (e.g., "Email already exists", "Passwords do not match", "Must accept terms"). Stay on Email Sign Up Screen.

3.  **Screen:** Select Current Role Screen (PRD Page 6)
    * **Info:** Presents a list or search interface for selecting the user's current job role.
    * **Action:** User searches for or selects their current role from the list. (F1.6)
    * **-> State Change:** Selection is confirmed visually. 'Next' or 'Continue' button enabled.
    * **Action:** User taps 'Next' or 'Continue'.
    * **-> Transition:** Navigate to Select Target Role Screen.

4.  **Screen:** Select Target Role Screen (PRD Page 7)
    * **Info:** Presents a list or search interface for selecting the user's desired target job role.
    * **Action:** User searches for or selects their target role from the list. (F1.6)
    * **-> State Change:** Selection is confirmed visually. 'Next' or 'Continue' button enabled.
    * **Action:** User taps 'Next' or 'Continue'.
    * **-> Transition:** Navigate to Select Interaction Preference Screen.

5.  **Screen:** Select Interaction Preference Screen (PRD Page 8)
    * **Info:** Presents options: "Mock Interviews", "Referral Exchange", "Both".
    * **Action:** User selects one of the interaction preferences. (F1.7)
    * **-> State Change:** Selection is confirmed visually. 'Finish' or 'Continue' button enabled.
    * **Action:** User taps 'Finish' or 'Continue'.
    * **-> System Event:** Profile setup is complete. User data saved.
    * **-> Transition:** Navigate to Main Matching/Discovery Screen.

6.  **Screen:** Main Matching/Discovery Screen (PRD Pages 9, 10)
    * **Info:** Onboarding complete. User sees the first potential match card based on initial criteria. (F2.1)

---

## Flow: Existing User Login (Email Primary)

* **Goal:** An existing user logs into their account using their email and password.
* **References:** PRD Sec 2 (Feature 1), User Story F1.4.

1.  **Screen:** Initial App Launch / Landing Screen (PRD Page 4)
    * **Info:** Displays options: "Sign Up with Email", "Log In", and potentially SSO options (F1.14 - Post-MVP). Includes "Forgot Password?" link (F1.5 - Post-MVP).
    * **Action:** User taps "Log In" button.
    * **-> Transition:** Navigate to Email Login Screen.

2.  **Screen:** Email Login Screen (Derived from PRD Page 4)
    * **Info:** Fields for Email and Password. Link for "Forgot Password?".
    * **Action:** User enters their registered Email and Password.
    * **-> State Change:** Input fields show entered data. 'Log In' button enabled.
    * **Action:** User taps 'Log In' button.
    * **-> System Event:** Backend authenticates credentials.
    * **-> Transition (Success):** User authenticated. Navigate to Main Matching/Discovery Screen.
    * **-> Transition (Failure):** Display error message ("Invalid email or password"). Stay on Email Login Screen.

3.  **Screen:** Main Matching/Discovery Screen (PRD Pages 9, 10)
    * **Info:** User is logged in and sees potential match cards. (F2.1)

*(Note: SSO Login (Apple/LinkedIn - F1.14) would follow a similar pattern but trigger the respective platform's authentication flow instead of showing the Email Login Screen).*

---

## Flow: Discovering & Matching (Swipe Loop)

* **Goal:** User browses potential matches and indicates interest, potentially resulting in a mutual match.
* **References:** PRD Sec 2 (Feature 2), PRD Sec 3 (Journey Map), User Stories F2.1, F2.2, F2.3, F2.4, F2.5, F2.6.

1.  **Screen:** Main Matching/Discovery Screen (PRD Pages 9, 10)
    * **Info:** Displays a profile card of a potential match (User B), showing Photo, Name, Roles, Location, Preference, Bio snippet (F2.3). May show Like/Pass buttons.
    * **Action (Like):** User swipes the card right OR taps the 'Like' button. (F2.2)
    * **-> System Event:** 'Like' action sent to backend. Backend checks for swipe limits (F2.5 - Free User) and mutual like (F2.4).
    * **-> Transition (Limit Reached - Free User):** Navigate to Likes Limit Reached Screen (F2.6).
    * **-> Transition (Mutual Like):** Navigate to "It's a Match!" Screen (F2.4).
    * **-> Transition (Like Recorded, No Match Yet):** Card animates off. Navigate to Main Matching/Discovery Screen (showing next card or empty state).
    * **Action (Pass):** User swipes the card left OR taps the 'Pass' button. (F2.2)
    * **-> System Event:** 'Pass' action sent to backend.
    * **-> Transition:** Card animates off. Navigate to Main Matching/Discovery Screen (showing next card or empty state).
    * **State (Empty):** If no more profiles meet criteria, display "No more profiles nearby" message. (F2.1)

2.  **Screen:** Likes Limit Reached Screen (PRD Page 24) (Applies to Free Tier Only)
    * **Info:** Informs user they've run out of likes, shows time until reset, provides "Upgrade to Premium" button (F2.6).
    * **Action:** User taps "Upgrade to Premium".
    * **-> Transition:** Navigate to Premium Subscription Screen (Flow: Upgrading to Premium).
    * **Action:** User dismisses the screen (if possible) or waits.
    * **-> Transition:** Return to Main Matching/Discovery Screen (Right swipe disabled until reset).

3.  **Screen:** "It's a Match!" Screen (PRD Page 17)
    * **Info:** Displays "It's a Match!" message with matched user's (User B) photo and name. Buttons for "Send a Message" and "Keep Swiping". (F2.4)
    * **Action:** User taps "Send a Message".
    * **-> Transition:** Navigate to Chat Screen with User B (Flow: Initiating & Engaging in Chat).
    * **Action:** User taps "Keep Swiping".
    * **-> Transition:** Navigate back to Main Matching/Discovery Screen (showing next card or empty state).

---

## Flow: Initiating & Engaging in Chat (Post-Match)

* **Goal:** User starts or continues a conversation with a matched user.
* **References:** PRD Sec 2 (Feature 3), PRD Sec 3 (Journey Map), User Stories F2.4, F3.1, F3.2, F3.3, F3.4.

1.  **Starting Point A:** "It's a Match!" Screen (PRD Page 17)
    * **Action:** User taps "Send a Message". (F2.4)
    * **-> Transition:** Navigate directly to Chat Screen with the matched user. (Proceed to Step 4).

2.  **Starting Point B:** Any Screen with Main Navigation
    * **Action:** User taps the "Chats" tab in the main navigation. (F3.1)
    * **-> Transition:** Navigate to Chats List Screen.

3.  **Screen:** Chats List Screen (PRD Page 11)
    * **Info:** Displays a list of existing matches/conversations. Each row shows match's photo, name, last message preview, timestamp, and unread indicator (F3.2). Shows empty state if no conversations.
    * **Action:** User taps on a specific conversation row. (F3.3)
    * **-> Transition:** Navigate to Chat Screen with the selected match.

4.  **Screen:** Chat Screen (PRD Page 20)
    * **Info:** Displays conversation history with the selected match chronologically. Messages show text, sender differentiation, and timestamps. Text input field and 'Send' button are visible at the bottom (F3.4).
    * **Action:** User types a message into the text input field.
    * **-> State Change:** Text appears in the input field. 'Send' button may become active.
    * **Action:** User taps the 'Send' button.
    * **-> System Event:** Message sent to backend/real-time service.
    * **-> State Change:** Message appears in the chat history (visually marked as own message). Input field clears.
    * **System Event (Incoming Message):** A new message arrives from the match.
    * **-> State Change:** New message appears in the chat history (visually marked as other user's message). Unread indicator updated if user is not on this screen. (F3.5 - Notifications are Post-MVP).

---

## Flow: Viewing & Editing User Profile

* **Goal:** User views their own profile and edits their information.
* **References:** PRD Sec 2 (Feature 1), User Stories F1.8, F1.9.

1.  **Screen:** Any Screen with Main Navigation/Profile Access
    * **Action:** User taps on their Profile tab or access point (e.g., profile icon in settings).
    * **-> Transition:** Navigate to View Profile Screen.

2.  **Screen:** View Profile Screen (Own Profile) (Derived from PRD Pages 14, 19)
    * **Info:** Displays the user's own Photo, Name, Location, Current Role, Target Role, Bio, Interaction Preference (F1.8). An "Edit Profile" button is visible.
    * **Action:** User taps the "Edit Profile" button. (F1.9)
    * **-> Transition:** Navigate to Edit Profile Screen.

3.  **Screen:** Edit Profile Screen (PRD Page 21)
    * **Info:** Displays current profile information in editable fields: Name, City, Bio (text area), Current Role (selector), Target Role (selector), Interaction Preference (selector). Option to change Profile Picture. Save/Cancel buttons visible.
    * **Action:** User modifies text fields (Name, City, Bio).
    * **Action:** User taps Role/Preference selectors -> Selects new value from list/options.
    * **Action:** User taps Profile Picture -> Uploads new image.
    * **-> State Change:** Edits are reflected in the input fields/image preview. 'Save' button may become active.
    * **Action:** User taps 'Save' button.
    * **-> System Event:** Backend updates the user's profile data.
    * **-> Transition (Success):** Changes saved. Navigate back to View Profile Screen (displaying updated info).
    * **-> Transition (Failure):** Show error message. Stay on Edit Profile Screen.
    * **Action:** User taps 'Cancel' or navigates back without saving.
    * **-> State Change (Optional Prompt):** "Discard changes?" Yes/No.
    * **-> Transition (Discard):** Navigate back to View Profile Screen (displaying original info).

4.  **Screen:** View Profile Screen (Own Profile)
    * **Info:** Displays the profile, reflecting any saved changes.

---

## Flow: Upgrading to Premium Subscription

* **Goal:** A free user purchases the Premium subscription.
* **References:** PRD Sec 2 (Feature 4), PRD Sec 3 (Journey Map), User Stories F2.6, F4.1-F4.6.

1.  **Starting Point A:** Likes Limit Reached Screen (PRD Page 24)
    * **Action:** User taps "Upgrade to Premium". (F2.6, F4.4)
    * **-> Transition:** Navigate to Premium Subscription Screen.

2.  **Starting Point B:** Attempting to Access Premium Feature (Free User)
    * **Action:** User taps "Likes" tab OR attempts to use Filters. (F4.4)
    * **-> Transition:** Navigate to Premium Subscription Screen (or an intermediary paywall screen linking to it).

3.  **Starting Point C:** Settings Screen (PRD Page 15)
    * **Action:** User navigates to Settings -> Taps "Get Premium" or similar option.
    * **-> Transition:** Navigate to Premium Subscription Screen.

4.  **Screen:** Premium Subscription Screen (PRD Page 23)
    * **Info:** Clearly lists Premium benefits (Unlimited Swipes, See Likes, Filters - F4.1, F4.2, F4.3), shows the price ($3.99/mo), and has a "Get Premium" / "Subscribe" button (F4.5).
    * **Action:** User taps "Get Premium" / "Subscribe". (F4.6)
    * **-> Transition:** Initiate platform-specific In-App Purchase flow (Apple App Store / Google Play Store).

5.  **Screen:** Platform In-App Purchase UI (OS Level)
    * **Info:** Native OS prompt showing subscription details, price, and asking for confirmation/authentication (e.g., Face ID, password, fingerprint).
    * **Action:** User confirms the purchase and authenticates.
    * **-> System Event:** Payment processed by Apple/Google. Receipt generated. App receives confirmation callback.
    * **-> Transition (Success):** Purchase successful. Return to Mockaccino app.
    * **-> Transition (Failure/Cancel):** Purchase failed or cancelled by user. Return to Mockaccino app.

6.  **Return to Mockaccino App (Post-Purchase Attempt)**
    * **System Event (Success):** App validates purchase receipt with backend. Backend updates user account status to Premium. (F4.6)
    * **-> State Change:** User status is now Premium. Premium features are unlocked.
    * **-> Transition (Success):** Navigate to a confirmation screen ("You're now Premium!") or back to the screen where upgrade was initiated (e.g., Main Matching Screen, Settings), with features now enabled.
    * **-> Transition (Failure):** Display an error message ("Purchase failed" or "Verification failed"). User remains Free Tier. Navigate back to Premium Subscription Screen or originating screen.

---

## Flow: Password Reset

* **Goal:** A user who forgot their password resets it via email.
* **References:** PRD Sec 2 (Feature 1), User Story F1.5 (Post-MVP).

1.  **Screen:** Email Login Screen (Derived from PRD Page 4)
    * **Action:** User taps the "Forgot Password?" link. (F1.5)
    * **-> Transition:** Navigate to Password Reset Request Screen.

2.  **Screen:** Password Reset Request Screen
    * **Info:** Field to enter the registered email address. "Send Reset Link" button.
    * **Action:** User enters their registered email address.
    * **Action:** User taps "Send Reset Link".
    * **-> System Event:** Backend validates email exists -> Generates secure reset token -> Sends email with reset link.
    * **-> Transition (Success):** Display confirmation message ("Password reset email sent. Check your inbox."). Stay on screen or navigate back to Login Screen.
    * **-> Transition (Failure):** Display error ("Email not found" or generic error). Stay on Password Reset Request Screen.

3.  **External:** User's Email Client
    * **Action:** User opens email -> Clicks the password reset link.
    * **-> Transition:** Opens a secure web page or deep link into the Mockaccino app's Password Reset Screen.

4.  **Screen:** Password Reset Screen (In-App or Web)
    * **Info:** Fields for New Password and Confirm New Password. "Reset Password" button.
    * **Action:** User enters a new strong password and confirms it.
    * **Action:** User taps "Reset Password".
    * **-> System Event:** Backend validates the reset token (from link) -> Validates new password strength/match -> Updates the user's password securely.
    * **-> Transition (Success):** Display success message ("Password successfully reset. You can now log in."). Navigate to Login Screen.
    * **-> Transition (Failure - Invalid Token):** Display error ("Invalid or expired reset link.").
    * **-> Transition (Failure - Password Rules):** Display error ("Passwords do not match" or "Password too weak."). Stay on Password Reset Screen.

5.  **Screen:** Email Login Screen
    * **Info:** User can now log in with their new password. (F1.4)
