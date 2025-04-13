# Mockaccino Mobile App - User Stories v1.0

This document outlines the user stories derived from the Mockaccino Mobile App PRD v1.0.

### Feature: User Authentication & Profile Management

**ID:** F1.1
**User Story:** As a new user, I want to sign up using my Email address, so that I can create a Mockaccino account using a common method.
**Priority:** MVP
**Dependencies:** None
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the initial app screen WHEN I tap the "Sign Up with Email" option THEN I am presented with the email sign-up form.
    2. GIVEN I am on the email sign-up form WHEN I enter a valid Full Name, valid unique Email, City, strong Password, confirm the Password, and check the 'Accept Terms' box THEN the 'Sign Up' button becomes enabled.
    3. GIVEN the sign-up form is validly filled WHEN I tap 'Sign Up' THEN my account is created, I am logged in, and navigated to the profile setup/onboarding flow (Select Role - F1.6).
    4. GIVEN I attempt to sign up with an email already in use WHEN I tap 'Sign Up' THEN an error message "Email already exists" is displayed, and the account is not created.
    5. GIVEN I enter an invalid email format WHEN I move focus from the email field THEN an inline validation error "Invalid email format" is shown.
    6. GIVEN I enter mismatching passwords WHEN I tap 'Sign Up' THEN an error message "Passwords do not match" is displayed.
    7. GIVEN I do not check the 'Accept Terms' box WHEN I tap 'Sign Up' THEN an error message "You must accept the Terms of Service" is displayed.
**Tasks:**
    * Design email sign-up screen UI/UX.
    * Implement frontend form for email sign-up (fields, validation).
    * Develop backend endpoint for user creation via email.
    * Implement logic to check for existing emails.
    * Implement password complexity rules and hashing.
    * Integrate frontend form with backend endpoint.
    * Implement navigation to the next onboarding step (F1.6) upon successful sign-up.
    * Write tests for email sign-up (frontend validation, backend logic, integration).
---
**ID:** F1.2
**User Story:** As a new user signing up with email, I must provide my Full Name, Email, City, and Password, and optionally upload a Profile Picture, so that my basic profile information is captured.
**Priority:** MVP
**Dependencies:** F1.1
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the email sign-up screen WHEN the required fields (Full Name, Email, City, Password, Confirm Password, Accept Terms) are not filled THEN the 'Sign Up' button is disabled.
    2. GIVEN I am on the email sign-up screen WHEN I tap the profile picture placeholder THEN I am prompted to upload an image (from camera or gallery).
    3. GIVEN I select an image WHEN the image is successfully uploaded THEN the placeholder is replaced with the selected image.
    4. GIVEN I choose not to upload an image WHEN I complete the sign-up process THEN a default profile picture/placeholder is used for my account.
    5. GIVEN I complete the sign-up process WHEN my profile is created THEN my Full Name, Email (secured), City, and Profile Picture (if provided) are stored.
**Tasks:**
    * Define required fields on the email sign-up form.
    * Implement profile picture upload functionality (client-side selection, API call).
    * Develop backend logic to handle optional profile picture upload during sign-up.
    * Implement default profile picture assignment if none is uploaded.
    * Ensure data persistence for the provided fields upon account creation.
    * Write tests for field validation and optional image upload.
---
**ID:** F1.3
**User Story:** As a new user, I must accept the Terms of Service and Privacy Policy, so that I acknowledge the app's rules and data usage before creating an account.
**Priority:** MVP
**Dependencies:** F1.1
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the sign-up screen WHEN I view the form THEN I see a checkbox or toggle labeled "I accept the Terms of Service and Privacy Policy".
    2. GIVEN the acceptance checkbox is present WHEN I tap on the "Terms of Service" link THEN the Terms of Service document is displayed (e.g., in-app webview or browser).
    3. GIVEN the acceptance checkbox is present WHEN I tap on the "Privacy Policy" link THEN the Privacy Policy document is displayed.
    4. GIVEN I have filled all other required sign-up fields WHEN the acceptance checkbox is unchecked THEN the 'Sign Up' button remains disabled or tapping it shows an error.
    5. GIVEN I have filled all other required sign-up fields WHEN I check the acceptance checkbox THEN the 'Sign Up' button becomes enabled (assuming other fields are valid).
**Tasks:**
    * Add checkbox/toggle for ToS/Privacy Policy acceptance to the sign-up UI.
    * Implement linking to the ToS and Privacy Policy documents.
    * Implement logic to enable/disable the sign-up button based on checkbox state.
    * Store acceptance status/timestamp upon successful sign-up (optional, for compliance).
    * Finalize and host ToS and Privacy Policy documents.
    * Write tests to verify checkbox requirement and link functionality.
---
**ID:** F1.4
**User Story:** As an existing user, I want to log in using my Email and Password, so that I can access my Mockaccino account.
**Priority:** MVP
**Dependencies:** F1.1
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the initial app screen WHEN I tap the "Log In" option THEN I am presented with the email/password login form.
    2. GIVEN I am on the login form WHEN I enter my registered Email and correct Password THEN the 'Log In' button is enabled.
    3. GIVEN I have entered valid credentials WHEN I tap 'Log In' THEN I am successfully authenticated and navigated to the main matching screen (F2.1).
    4. GIVEN I enter an incorrect password WHEN I tap 'Log In' THEN an error message "Invalid email or password" is displayed.
    5. GIVEN I enter an email address not associated with an account WHEN I tap 'Log In' THEN an error message "Invalid email or password" is displayed.
**Tasks:**
    * Design login screen UI/UX.
    * Implement frontend form for email/password login.
    * Develop backend endpoint for user authentication via email/password.
    * Implement secure password comparison logic.
    * Handle authentication success (session/token management) and failure (error display).
    * Implement navigation to the main screen upon successful login.
    * Write tests for login functionality (success, incorrect password, non-existent user).
---
**ID:** F1.5
**User Story:** As a user who forgot their password, I want a way to reset it, so that I can regain access to my account.
**Priority:** Post-MVP
**Dependencies:** F1.1, F1.4
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the login screen WHEN I tap the "Forgot Password?" link THEN I am navigated to the password reset request screen.
    2. GIVEN I am on the password reset request screen WHEN I enter my registered email address AND tap "Send Reset Link" THEN a confirmation message is displayed, and an email with a password reset link is sent to my address.
    3. GIVEN I have received the password reset email WHEN I click the reset link THEN I am taken to a secure page (in-app or web) to enter a new password.
    4. GIVEN I am on the new password page WHEN I enter a new strong password, confirm it, and tap "Reset Password" THEN my password is updated, and I see a success message.
    5. GIVEN I attempt to reset the password with an unregistered email WHEN I tap "Send Reset Link" THEN an error message "Email not found" is displayed (or a generic message for security).
    6. GIVEN I try to use an expired or invalid reset link WHEN I access the link THEN I am shown an error message indicating the link is invalid or expired.
**Tasks:**
    * Design UI/UX for Forgot Password flow (request screen, reset screen, email template).
    * Implement frontend for password reset request (email input).
    * Develop backend endpoint to generate and email a secure, time-limited password reset token/link.
    * Develop backend endpoint to validate the reset token and update the user's password.
    * Implement secure password complexity rules for the new password.
    * Integrate email sending service.
    * Write tests for the entire password reset flow.
---
**ID:** F1.6
**User Story:** As a new user during onboarding, I want to select my Current Role and Target Role, so that the app can help find relevant matches for me.
**Priority:** MVP
**Dependencies:** F1.1 (or F1.12/F1.13 if implemented first)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I have successfully signed up (or logged in via SSO for the first time) WHEN I proceed with onboarding THEN I am presented with a screen to select my "Current Role".
    2. GIVEN I am on the "Current Role" selection screen WHEN I search or select a role from a predefined list THEN my selection is registered.
    3. GIVEN I have selected my Current Role WHEN I proceed THEN I am presented with a screen to select my "Target Role".
    4. GIVEN I am on the "Target Role" selection screen WHEN I search or select a role from a predefined list THEN my selection is registered.
    5. GIVEN I have selected both roles WHEN I proceed THEN these roles are saved to my profile and I am navigated to the next onboarding step (F1.7).
**Tasks:**
    * Design UI/UX for role selection screens (potentially combined).
    * Define and populate the list of selectable roles (consider search/autocomplete).
    * Implement frontend components for role selection.
    * Develop backend logic to store selected roles in the user profile.
    * Implement navigation between onboarding steps.
    * Write tests for role selection and persistence.
---
**ID:** F1.7
**User Story:** As a new user during onboarding, I want to specify if I'm interested in Referral Exchange, Mock Interviews, or Both, so that I am matched with users seeking compatible interactions.
**Priority:** MVP
**Dependencies:** F1.6
**Acceptance Criteria / Test Steps:**
    1. GIVEN I have completed the role selection step (F1.6) WHEN I proceed with onboarding THEN I am presented with a screen to select my "Interaction Preference".
    2. GIVEN I am on the Interaction Preference screen WHEN I select "Referral Exchange", "Mock Interviews", or "Both" THEN my selection is registered.
    3. GIVEN I have made a selection WHEN I proceed THEN my preference is saved to my profile, and I am navigated to the main matching screen (completing onboarding).
**Tasks:**
    * Design UI/UX for Interaction Preference selection screen.
    * Implement frontend component for selecting the preference (e.g., radio buttons, toggle).
    * Develop backend logic to store the selected preference in the user profile.
    * Implement navigation to the main app screen upon completion.
    * Write tests for preference selection and persistence.
---
**ID:** F1.8
**User Story:** As a user, I want my profile screen to display my Photo, Name, Location (City), Current Role, Target Role, Bio, and Interaction Preference, so that I and others can view my key professional details.
**Priority:** MVP
**Dependencies:** F1.1, F1.2, F1.6, F1.7
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am logged in WHEN I navigate to my profile screen THEN I see my uploaded Profile Picture (or default).
    2. GIVEN I am on my profile screen THEN I see my Full Name.
    3. GIVEN I am on my profile screen THEN I see my Location (City).
    4. GIVEN I am on my profile screen THEN I see my selected Current Role.
    5. GIVEN I am on my profile screen THEN I see my selected Target Role.
    6. GIVEN I am on my profile screen THEN I see my Bio (initially empty or placeholder text).
    7. GIVEN I am on my profile screen THEN I see my selected Interaction Preference (Referral Exchange/Mock Interviews/Both).
    8. GIVEN I am viewing another user's profile (e.g., after a match) THEN I see their corresponding information (Photo, Name, City, Roles, Bio, Preference).
**Tasks:**
    * Design UI/UX for the user profile screen (view mode).
    * Implement frontend component to display profile data.
    * Develop backend endpoint to fetch user profile data (own and others').
    * Ensure data fetched during onboarding/sign-up is correctly displayed.
    * Handle display of optional fields (e.g., default picture, empty bio).
    * Write tests for profile data fetching and display.
---
**ID:** F1.9
**User Story:** As a user, I want to be able to edit all aspects of my profile (Photo, Name, City, Roles, Bio, Interaction Preference) after creation, so that I can keep my information up-to-date.
**Priority:** MVP
**Dependencies:** F1.8
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am viewing my own profile screen (F1.8) WHEN I tap an "Edit" button or specific fields THEN I enter profile edit mode.
    2. GIVEN I am in edit mode WHEN I change my Full Name, City, or Bio text AND tap "Save" THEN the changes are saved and reflected on my profile view.
    3. GIVEN I am in edit mode WHEN I tap to change my Profile Picture THEN I can upload a new image, and upon saving, it updates my profile.
    4. GIVEN I am in edit mode WHEN I tap to change my Current Role or Target Role THEN I can select new roles from the list, and upon saving, they update my profile.
    5. GIVEN I am in edit mode WHEN I tap to change my Interaction Preference THEN I can select a new preference, and upon saving, it updates my profile.
    6. GIVEN I make changes and attempt to navigate away without saving WHEN prompted THEN I can choose to save or discard changes.
**Tasks:**
    * Design UI/UX for profile editing mode.
    * Implement frontend components for editing profile fields (text inputs, picture upload, role/preference selectors).
    * Develop backend endpoint(s) to update user profile data.
    * Implement save/cancel logic and confirmation prompts.
    * Ensure edited data is correctly persisted and displayed.
    * Write tests for editing each profile field and the save/cancel functionality.
---
**ID:** F1.10
**User Story:** As a user, I want to be able to log out of my account, so that I can securely end my session on the device.
**Priority:** MVP
**Dependencies:** F1.4 (or F1.1/F1.12/F1.13)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am logged into the app WHEN I navigate to the Settings screen (F5.1) THEN I see a "Log Out" option.
    2. GIVEN I see the "Log Out" option WHEN I tap it THEN I am prompted with a confirmation message (e.g., "Are you sure you want to log out?").
    3. GIVEN I confirm logging out WHEN I tap "Confirm" or "Yes" THEN my session is terminated, local session data is cleared, and I am returned to the initial sign-up/login screen.
    4. GIVEN I have logged out WHEN I relaunch the app THEN I am presented with the sign-up/login screen, not my previous session.
**Tasks:**
    * Add a "Log Out" button/link to the Settings screen UI.
    * Implement confirmation dialog for logout.
    * Implement client-side logic to clear user session/token data.
    * Implement navigation back to the initial auth screen.
    * Write tests to verify logout functionality and session termination.
---
**ID:** F1.11
**User Story:** As a user, I want the option to deactivate my account, so that my profile is no longer visible and my data is handled according to the privacy policy.
**Priority:** Future
**Dependencies:** F1.10, F5.1
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am logged in WHEN I navigate to the Settings screen THEN I see an "Account Settings" or similar section.
    2. GIVEN I am in Account Settings WHEN I find the "Deactivate Account" option AND tap it THEN I am presented with information about deactivation consequences and a confirmation step.
    3. GIVEN I confirm deactivation WHEN I complete the process THEN my account is marked as inactive, my profile is hidden from other users, I am logged out, and potentially scheduled for deletion based on policy.
    4. GIVEN my account is deactivated WHEN I try to log in THEN I receive a message indicating the account is inactive or does not exist.
**Tasks:**
    * Design UI/UX for account deactivation flow (including warnings/confirmation).
    * Implement frontend elements for initiating deactivation.
    * Develop backend logic to mark an account as inactive (soft delete).
    * Implement logic to hide deactivated profiles from matching and search.
    * Define data retention policy for deactivated accounts.
    * Write tests for account deactivation and login attempts post-deactivation.
---
**ID:** F1.12
**User Story:** As a new user, I want to sign up using my Apple ID, so that I can create a Mockaccino account quickly and securely using my existing Apple credentials.
**Priority:** Post-MVP
**Dependencies:** None (Parallel to F1.1)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the initial app screen WHEN I tap the "Sign Up with Apple" option THEN the native Apple Sign-In flow is initiated.
    2. GIVEN I successfully authenticate with Apple Sign-In (potentially hiding my email) WHEN required information (Name, Email if shared) is received THEN my Mockaccino account is created using this information.
    3. GIVEN the account is created WHEN I am logged in THEN I am navigated to the profile setup/onboarding flow (Select Role - F1.6).
    4. GIVEN Apple Sign-In provides necessary data (Name, Email) WHEN onboarding is complete THEN this data is pre-filled in my profile where applicable.
**Tasks:**
    * Integrate Apple Sign-In SDK/API.
    * Implement frontend button/logic to trigger Apple Sign-In.
    * Develop backend logic to handle Apple Sign-In callbacks, create user accounts, and manage Apple-specific user identifiers.
    * Handle cases where users hide their email via Apple Sign-In (use provided private relay email).
    * Map Apple Sign-In data to the user profile model.
    * Implement navigation to onboarding (F1.6).
    * Write tests for Apple Sign-In success and failure scenarios.
---
**ID:** F1.13
**User Story:** As a new user, I want to sign up using my LinkedIn account, so that I can create a Mockaccino account quickly using my professional network credentials and potentially pre-fill profile information.
**Priority:** Post-MVP
**Dependencies:** None (Parallel to F1.1)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the initial app screen WHEN I tap the "Sign Up with LinkedIn" option THEN the LinkedIn OAuth flow is initiated.
    2. GIVEN I successfully authenticate with LinkedIn and grant necessary permissions WHEN required information (e.g., Name, Email, Profile Picture, Headline/Current Role) is received THEN my Mockaccino account is created using this information.
    3. GIVEN the account is created WHEN I am logged in THEN I am navigated to the profile setup/onboarding flow (Select Role - F1.6).
    4. GIVEN LinkedIn provides relevant data WHEN onboarding/profile editing occurs THEN this data can be used to pre-fill or suggest information for my Mockaccino profile (e.g., Name, Picture, Current Role).
**Tasks:**
    * Register app with LinkedIn Developer platform and obtain API keys.
    * Integrate LinkedIn OAuth SDK/API.
    * Implement frontend button/logic to trigger LinkedIn Sign-In.
    * Develop backend logic to handle LinkedIn OAuth callbacks, create user accounts, and manage LinkedIn-specific user identifiers.
    * Define required LinkedIn profile scopes (e.g., basic profile, email).
    * Map LinkedIn profile data to the Mockaccino user profile model.
    * Implement navigation to onboarding (F1.6).
    * Write tests for LinkedIn Sign-In success and failure scenarios.
---
**ID:** F1.14
**User Story:** As an existing user, I want to log in using my linked Apple ID or LinkedIn account, so that I can access my account without entering my email/password.
**Priority:** Post-MVP
**Dependencies:** F1.12, F1.13
**Acceptance Criteria / Test Steps:**
    1. GIVEN I previously signed up or linked my account using Apple ID WHEN I tap "Log In with Apple" on the login screen THEN I am authenticated via Apple Sign-In and logged into my existing Mockaccino account.
    2. GIVEN I previously signed up or linked my account using LinkedIn WHEN I tap "Log In with LinkedIn" on the login screen THEN I am authenticated via LinkedIn OAuth and logged into my existing Mockaccino account.
    3. GIVEN I attempt to log in via SSO (Apple/LinkedIn) but no matching Mockaccino account exists THEN I am prompted to sign up or informed that no account is linked.
**Tasks:**
    * Implement frontend buttons for "Log In with Apple" and "Log In with LinkedIn".
    * Develop backend logic to authenticate users via SSO providers and match them to existing accounts based on provider ID or verified email.
    * Handle session management upon successful SSO login.
    * Implement error handling for cases where no account is found for the SSO login attempt.
    * Write tests for SSO login success and failure scenarios for existing users.

### Feature: Matching & Discovery

**ID:** F2.1
**User Story:** As a user, I want to see potential matches presented as profile cards, one at a time, on the main screen, so that I can easily browse and evaluate potential connections.
**Priority:** MVP
**Dependencies:** F1.7 (Onboarding completion), F1.8 (Profile data for cards)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am logged in and have completed onboarding WHEN I land on the main app screen THEN I see a profile card displaying another user's information.
    2. GIVEN a profile card is displayed WHEN I interact with it (swipe left/right) THEN the next potential match's profile card is displayed.
    3. GIVEN there are no more potential matches meeting the basic criteria WHEN I am on the main screen THEN I see a message indicating "No more profiles nearby" or similar.
**Tasks:**
    * Design UI/UX for the profile card and the main matching screen layout.
    * Implement frontend component for displaying a profile card.
    * Develop backend logic/API endpoint to fetch potential matches based on basic criteria (e.g., opposite interaction preference, excluding self, excluding already swiped).
    * Implement frontend logic to fetch and display cards sequentially.
    * Handle the state where no more profiles are available.
    * Write tests for fetching and displaying profile cards.
---
**ID:** F2.2
**User Story:** As a user, I want to swipe right on a profile card to indicate interest (like) or swipe left to pass, so that I can express my preference for connecting with the displayed user.
**Priority:** MVP
**Dependencies:** F2.1
**Acceptance Criteria / Test Steps:**
    1. GIVEN a profile card is displayed (F2.1) WHEN I swipe the card to the right THEN the swipe is registered as a 'like', and the next card is shown.
    2. GIVEN a profile card is displayed WHEN I swipe the card to the left THEN the swipe is registered as a 'pass', and the next card is shown.
    3. GIVEN I swipe right or left WHEN the action is performed THEN the corresponding user ID and swipe direction are recorded.
    4. GIVEN UI elements exist (e.g., 'X' and 'Heart' buttons) WHEN I tap the 'Heart' button THEN it registers a 'like' swipe.
    5. GIVEN UI elements exist WHEN I tap the 'X' button THEN it registers a 'pass' swipe.
**Tasks:**
    * Implement swipe gesture recognition (left/right) on the profile card component.
    * Implement optional UI buttons (like/pass) as alternatives to swiping.
    * Develop backend endpoint to record swipe actions (swiperUserId, swipedUserId, direction).
    * Connect frontend swipe/button actions to the backend endpoint.
    * Ensure smooth transition/animation to the next card after a swipe.
    * Write tests for swipe registration (left/right) and button actions.
---
**ID:** F2.3
**User Story:** As a user viewing a profile card, I want it to display key information: Photo, Name, Age (if available/applicable), Current Role, Target Role, Location (City), Interaction Preference, and a Bio snippet, so that I can quickly assess compatibility.
**Priority:** MVP
**Dependencies:** F2.1, F1.8
**Acceptance Criteria / Test Steps:**
    1. GIVEN a profile card is displayed for User B WHEN I view it THEN I see User B's primary Profile Photo.
    2. GIVEN a profile card is displayed THEN I see User B's Full Name.
    3. GIVEN a profile card is displayed THEN I see User B's Location (City).
    4. GIVEN a profile card is displayed THEN I see User B's Current Role.
    5. GIVEN a profile card is displayed THEN I see User B's Target Role.
    6. GIVEN a profile card is displayed THEN I see User B's Interaction Preference (Mock Interview/Referral Exchange/Both).
    7. GIVEN User B has a Bio WHEN their profile card is displayed THEN I see the beginning portion (snippet) of their Bio.
    8. (Optional - If Age is implemented) GIVEN User B's age is available WHEN their profile card is displayed THEN I see their Age.
**Tasks:**
    * Design the layout of information within the profile card UI.
    * Ensure the backend endpoint fetching potential matches (from F2.1) includes all required data fields.
    * Implement frontend logic to correctly map and display fetched data onto the card component.
    * Implement logic for truncating the Bio to a snippet.
    * Handle display if certain optional data (like Bio) is missing.
    * Write tests to verify all specified data points are displayed correctly on the card.
---
**ID:** F2.4
**User Story:** As a user, I want to be notified with an "It's a Match!" screen when mutual interest occurs (I swipe right on someone who also swiped right on me), so that I know we can now chat.
**Priority:** MVP
**Dependencies:** F2.2
**Acceptance Criteria / Test Steps:**
    1. GIVEN User A swipes right on User B (F2.2).
    2. GIVEN User B has previously swiped right on User A.
    3. WHEN User A swipes right on User B THEN an "It's a Match!" screen is immediately displayed to User A, showing User B's profile picture and name.
    4. GIVEN the "It's a Match!" screen is displayed THEN options like "Send a Message" and "Keep Swiping" are presented.
    5. GIVEN a match occurs WHEN the backend processes the swipe THEN a match record is created linking User A and User B.
    6. GIVEN User B swipes right on User A AFTER User A has already swiped right on User B THEN the "It's a Match!" screen is displayed to User B.
**Tasks:**
    * Design UI/UX for the "It's a Match!" screen.
    * Implement backend logic to check for mutual likes upon receiving a 'like' swipe (F2.2).
    * Implement backend logic to create a `Match` record upon mutual like detection.
    * Implement frontend logic to display the "It's a Match!" screen when a match event is triggered (e.g., via API response).
    * Implement navigation options ("Send a Message" -> F3.3/F3.4, "Keep Swiping" -> F2.1).
    * Write tests for match detection logic and "It's a Match!" screen display.
---
**ID:** F2.5
**User Story:** As a user on the free tier, I want to understand that I have a limited number of right swipes per day/period, so that I know the constraints of the free plan.
**Priority:** MVP
**Dependencies:** F2.2
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am a free user WHEN I perform right swipes THEN my remaining swipe count for the period decreases.
    2. GIVEN I am a free user WHEN I run out of right swipes for the current period THEN I am prevented from performing further right swipes.
    3. GIVEN I attempt to swipe right after reaching the limit THEN the swipe action fails, and I am presented with the limit reached screen (F2.6).
    4. GIVEN a new period starts (e.g., after 24 hours) WHEN I access the app THEN my right swipe allowance is reset to the daily limit.
**Tasks:**
    * Define the daily right swipe limit for free users.
    * Implement backend logic to track right swipe usage per user per period.
    * Implement backend logic to enforce the swipe limit (reject 'like' swipes if limit reached).
    * Implement backend logic/scheduled job to reset swipe counts periodically.
    * Ensure the frontend receives appropriate feedback when a swipe is denied due to limits.
    * Write tests for swipe tracking, limit enforcement, and count reset.
---
**ID:** F2.6
**User Story:** As a user who runs out of likes, I want to see a screen informing me that I've reached my limit and prompting me to wait or upgrade to Premium, so that I understand my options.
**Priority:** MVP
**Dependencies:** F2.5
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am a free user and have used all my right swipes for the period (F2.5) WHEN I attempt to swipe right THEN a screen or overlay appears.
    2. GIVEN the "limit reached" screen is displayed THEN it clearly states that I've run out of likes for the day/period.
    3. GIVEN the "limit reached" screen is displayed THEN it shows the time remaining until my likes reset.
    4. GIVEN the "limit reached" screen is displayed THEN it presents an option/button to "Upgrade to Premium" (linking to F4.5).
    5. GIVEN the "limit reached" screen is displayed WHEN I dismiss it (if possible) THEN I return to the matching screen but cannot swipe right.
**Tasks:**
    * Design UI/UX for the "Likes Limit Reached" screen/overlay.
    * Implement frontend logic to display this screen when a swipe attempt fails due to limits (based on API response from F2.5).
    * Implement frontend logic to calculate and display the remaining time until reset.
    * Add a button/link navigating to the Premium subscription screen (F4.5).
    * Write tests for the display and content of the limit reached screen.

### Feature: Chat

**ID:** F3.1
**User Story:** As a user, I want a dedicated "Chats" tab listing all my ongoing conversations with matches, so that I can easily find and access my communications.
**Priority:** MVP
**Dependencies:** F2.4 (Need matches to have chats)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am logged in WHEN I view the main app interface THEN I see a distinct "Chats" tab or navigation item.
    2. GIVEN I have one or more matches (F2.4) WHEN I navigate to the "Chats" tab THEN I see a list of my matches with whom I can potentially chat.
    3. GIVEN I have sent or received messages with a match WHEN I view the "Chats" tab THEN that conversation appears in the list.
    4. GIVEN I have no matches or conversations WHEN I view the "Chats" tab THEN I see an empty state message (e.g., "Your matches will appear here").
**Tasks:**
    * Design UI/UX for the main navigation, including the "Chats" tab.
    * Design UI/UX for the chat list screen.
    * Implement frontend navigation structure.
    * Develop backend endpoint to fetch the list of user's matches/conversations.
    * Implement frontend logic to fetch and display the chat list.
    * Implement empty state display.
    * Write tests for fetching and displaying the chat list and empty state.
---
**ID:** F3.2
**User Story:** As a user viewing the chat list, I want each entry to show the match's name, profile picture, the preview of the last message, the timestamp of the last message, and an indicator for unread messages, so that I can quickly scan my conversations.
**Priority:** MVP
**Dependencies:** F3.1
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the "Chats" tab (F3.1) with active conversations WHEN I view the list THEN each conversation row displays the matched user's profile picture.
    2. GIVEN I view a conversation row THEN it displays the matched user's name.
    3. GIVEN messages have been exchanged in a conversation WHEN I view its row THEN it displays a truncated preview of the most recent message text.
    4. GIVEN messages have been exchanged WHEN I view its row THEN it displays the timestamp of the most recent message (e.g., "10:30 AM", "Yesterday", "Apr 10").
    5. GIVEN I have received new messages in a conversation that I haven't opened WHEN I view its row THEN an indicator (e.g., a badge with a count, a bold font) highlights the unread status.
    6. GIVEN all messages in a conversation have been read WHEN I view its row THEN there is no unread indicator.
**Tasks:**
    * Design UI/UX for individual rows in the chat list.
    * Ensure the backend endpoint (from F3.1) provides all necessary data (match name, picture URL, last message text, timestamp, unread count/status).
    * Implement frontend component for a chat list row.
    * Implement logic for formatting timestamps appropriately.
    * Implement logic for displaying unread indicators.
    * Implement message truncation for the preview.
    * Write tests for correct data display and unread indication in chat list rows.
---
**ID:** F3.3
**User Story:** As a user, I want to tap on a conversation in the chat list, so that I can open the full chat screen for that specific match.
**Priority:** MVP
**Dependencies:** F3.1
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the "Chats" tab (F3.1) viewing my conversation list WHEN I tap on a specific conversation row THEN I am navigated to the dedicated chat screen (F3.4) for that match.
    2. GIVEN I tap on a conversation row WHEN the chat screen opens THEN it displays the conversation history with that specific match.
**Tasks:**
    * Implement tap/click handlers on chat list rows.
    * Implement navigation logic from the chat list screen to the individual chat screen.
    * Ensure the correct match identifier is passed to the chat screen component.
    * Write tests for navigating from the list to the chat screen.
---
**ID:** F3.4
**User Story:** As a user within a chat screen, I want an interface displaying messages chronologically, sender identification, timestamps for messages, and an input field to type and send new messages, so that I can effectively communicate with my match.
**Priority:** MVP
**Dependencies:** F3.3
**Acceptance Criteria / Test Steps:**
    1. GIVEN I have opened a chat screen with a match (F3.3) WHEN I view the screen THEN messages are displayed in chronological order (oldest at the top or bottom, consistently).
    2. GIVEN messages are displayed THEN my messages are visually distinct from the match's messages (e.g., alignment, background color).
    3. GIVEN messages are displayed THEN each message bubble shows the message text.
    4. GIVEN messages are displayed THEN timestamps are shown for messages (e.g., grouped by time, shown per message).
    5. GIVEN I am on the chat screen THEN a text input field is visible and enabled.
    6. GIVEN I type text into the input field WHEN I tap the "Send" button THEN the message text is cleared from the input, the message appears in the chat history, and it is sent to the recipient.
    7. GIVEN a message is sent successfully WHEN the recipient receives it THEN it appears in their chat screen with the sender identified.
**Tasks:**
    * Design UI/UX for the individual chat screen (message bubbles, input area).
    * Implement frontend component for the chat screen.
    * Develop backend logic/API endpoint to fetch message history for a specific match.
    * Develop backend logic/real-time mechanism (e.g., WebSockets, Firestore listeners) to send and receive messages.
    * Implement frontend logic to display messages chronologically with sender differentiation and timestamps.
    * Implement frontend text input and "Send" button functionality.
    * Connect frontend message sending to the backend API/real-time service.
    * Implement real-time updates to display incoming messages.
    * Write tests for fetching history, sending messages, and receiving messages in real-time.
---
**ID:** F3.5
**User Story:** As a user, I want to receive notifications (in-app and potentially push) for new messages, so that I am promptly informed about updates in my conversations even when not actively using the chat screen.
**Priority:** Post-MVP
**Dependencies:** F3.4
**Acceptance Criteria / Test Steps:**
    1. GIVEN I have matched with User B and the app is backgrounded or closed WHEN User B sends me a message THEN I receive a push notification on my device displaying the sender's name and message snippet.
    2. GIVEN I have the app open but am not on the chat screen for User B WHEN User B sends me a message THEN I see an in-app notification (e.g., a banner) and the unread indicator updates on the Chats tab (F3.2).
    3. GIVEN I receive a push notification for a new message WHEN I tap on the notification THEN the app opens directly to the chat screen (F3.4) with that sender.
    4. GIVEN I receive a new message WHEN I am already on the chat screen with that sender THEN the new message appears directly in the chat history without a separate notification.
**Tasks:**
    * Integrate push notification services (FCM for Android, APNS for iOS).
    * Develop backend logic to trigger push notifications upon sending a message to an offline/backgrounded user.
    * Develop backend logic to trigger in-app notifications/updates for online users not on the specific chat screen.
    * Implement client-side handling of incoming push notifications (display, navigation on tap).
    * Implement client-side display of in-app notifications.
    * Manage notification permissions requests.
    * Write tests for receiving push and in-app notifications under different app states.

### Feature: Premium Features & Subscription

**ID:** F4.1
**User Story:** As a Premium user, I want to have unlimited right swipes, so that I am not restricted in how many potential connections I can express interest in per day.
**Priority:** Post-MVP
**Dependencies:** F4.6 (Requires ability to become Premium), F2.5 (Relaxes this constraint)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am a user with an active Premium subscription WHEN I perform right swipes THEN my swipe count is not decremented or checked against a daily limit.
    2. GIVEN I am a Premium user WHEN I continuously swipe right THEN I do not encounter the "Likes Limit Reached" screen (F2.6).
    3. GIVEN my Premium subscription expires WHEN I attempt to swipe right after using the free daily limit THEN the limit is enforced again (F2.5).
**Tasks:**
    * Modify backend swipe logic (F2.5) to bypass the limit check for users flagged as 'Premium'.
    * Ensure user subscription status is readily available when processing swipes.
    * Write tests to verify that Premium users can swipe right without limit and that the limit is reapplied upon subscription expiry.
---
**ID:** F4.2
**User Story:** As a Premium user, I want to access a "Likes" tab to see a list of users who have swiped right on my profile, so that I can directly see who is interested in me and choose to match with them instantly.
**Priority:** Post-MVP
**Dependencies:** F4.6 (Requires ability to become Premium), F2.2 (Needs users to swipe right)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am a user with an active Premium subscription WHEN I view the main app interface THEN I see a distinct "Likes" tab or navigation item.
    2. GIVEN other users have swiped right on my profile WHEN I navigate to the "Likes" tab THEN I see a grid or list of profile cards/summaries for those users.
    3. GIVEN I am viewing the "Likes" list WHEN I tap on a user's card THEN I can potentially view their full profile (details TBD) or swipe right/left on them directly from this screen.
    4. GIVEN I swipe right on a user from the "Likes" list WHEN the swipe is processed THEN it immediately results in a match (F2.4), and the user is removed from the "Likes" list.
    5. GIVEN I swipe left on a user from the "Likes" list WHEN the swipe is processed THEN the user is removed from the "Likes" list, and no match occurs.
**Tasks:**
    * Design UI/UX for the "Likes" tab/screen (grid or list view).
    * Add the "Likes" tab to the main navigation for Premium users.
    * Develop backend endpoint to fetch the list of users who have liked the current (Premium) user and haven't been swiped on yet by the current user.
    * Implement frontend logic to display the list of likers.
    * Implement swipe right/left functionality directly on the "Likes" screen, triggering instant matches on right swipe.
    * Update backend logic to handle swipes originating from the "Likes" screen and update the liker list accordingly.
    * Write tests for fetching likers, displaying them, and matching/dismissing from the Likes screen.
---
**ID:** F4.3
**User Story:** As a Premium user, I want to apply filters to my potential matches based on Role (Current/Target), Interview Preference, Search Distance, and City, so that I can narrow down my discovery queue to the most relevant candidates.
**Priority:** Post-MVP
**Dependencies:** F4.6 (Requires ability to become Premium), F2.1 (Applies filters to this)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am a user with an active Premium subscription WHEN I am on the main matching screen (F2.1) or a dedicated filter screen THEN I can access filter options.
    2. GIVEN I access the filters WHEN I select criteria for Current Role, Target Role, Interaction Preference, Search Distance (e.g., slider), or City THEN my selections are registered.
    3. GIVEN I apply the selected filters WHEN I return to the matching screen (F2.1) THEN the profile cards presented are only for users who meet the specified filter criteria.
    4. GIVEN I have active filters WHEN viewing the matching screen THEN there is a visual indicator showing that filters are active.
    5. GIVEN I can access the filters again WHEN I choose to clear or modify the filters THEN the matching queue updates accordingly.
**Tasks:**
    * Design UI/UX for accessing and configuring filters.
    * Implement frontend components for filter selection (role selectors, preference toggles, distance slider, city input).
    * Modify the backend endpoint for fetching potential matches (F2.1) to accept and apply filter parameters (roles, preference, location proximity, city).
    * Implement frontend logic to store active filters and pass them to the backend when fetching profiles.
    * Implement visual indication of active filters.
    * Implement logic for clearing filters.
    * Write tests for applying various filter combinations and verifying the results in the matching queue.
---
**ID:** F4.4
**User Story:** As a free user, I want to see prompts to upgrade to Premium when I try to access premium features (like the "Likes" tab or filters) or when I run out of likes, so that I am aware of the benefits and how to get them.
**Priority:** Post-MVP (tied to the release of Premium features)
**Dependencies:** F2.6, F4.1, F4.2, F4.3, F4.5
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am a free user WHEN I tap on the "Likes" tab (if visible) THEN I am presented with a screen promoting Premium (F4.5) instead of the actual Likes list (F4.2).
    2. GIVEN I am a free user WHEN I attempt to access the advanced filters feature (F4.3) THEN I am presented with a screen promoting Premium (F4.5).
    3. GIVEN I am a free user and run out of likes WHEN the "limit reached" screen (F2.6) is displayed THEN it includes a prominent call-to-action to upgrade to Premium, linking to the Premium screen (F4.5).
**Tasks:**
    * Implement conditional logic on the frontend to check user subscription status before granting access to Premium features ("Likes" tab, Filters UI).
    * Implement navigation to the Premium subscription screen (F4.5) from these access points/prompts.
    * Ensure the "Likes Limit Reached" screen (F2.6) includes the upgrade prompt.
    * Write tests to verify that free users are correctly prompted to upgrade when accessing premium features or hitting the like limit.
---
**ID:** F4.5
**User Story:** As a user, I want a dedicated screen clearly outlining the benefits (Unlimited Swipes, See Likes, Filters) and cost ($3.99/mo) of the Premium subscription, so that I can make an informed decision about upgrading.
**Priority:** Post-MVP
**Dependencies:** F4.1, F4.2, F4.3 (Defines the benefits)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I navigate to the Premium subscription screen (e.g., via prompts F4.4, or a settings link) WHEN the screen loads THEN it clearly lists the key benefits: "Unlimited Right Swipes", "See Who Likes You", "Advanced Filters".
    2. GIVEN the Premium screen is displayed THEN it clearly states the subscription price (e.g., "$3.99 per month").
    3. GIVEN the Premium screen is displayed THEN it includes a clear call-to-action button like "Get Premium" or "Subscribe Now" (leading to F4.6).
    4. GIVEN the Premium screen is displayed THEN it may include links to terms related to subscriptions or auto-renewal.
**Tasks:**
    * Design UI/UX for the Premium subscription marketing/purchase screen.
    * Implement the frontend component for this screen.
    * Ensure the content accurately reflects the Premium features (F4.1, F4.2, F4.3) and the defined price.
    * Add navigation points to this screen (from prompts, settings, etc.).
    * Write tests to verify the content (benefits, price) and presence of the purchase button.
---
**ID:** F4.6
**User Story:** As a user, I want to be able to securely purchase the Premium subscription using standard payment methods (e.g., platform-specific in-app purchases), so that I can unlock premium features.
**Priority:** Post-MVP
**Dependencies:** F4.5
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the Premium subscription screen (F4.5) WHEN I tap the "Get Premium" or "Subscribe" button THEN the platform's standard in-app purchase flow is initiated (Apple App Store / Google Play Store).
    2. GIVEN I successfully complete the payment process via the platform's purchase flow WHEN the purchase is confirmed THEN my Mockaccino account is updated to Premium status.
    3. GIVEN my account is updated to Premium WHEN I return to the app THEN premium features (Unlimited Likes F4.1, Likes Tab F4.2, Filters F4.3) are immediately unlocked.
    4. GIVEN the payment process fails or is cancelled WHEN I return to the app THEN my account remains on the free tier, and an appropriate message may be shown.
    5. GIVEN I have an active subscription WHEN I revisit the Premium screen THEN it reflects my current status (e.g., shows expiry date, manage subscription options).
**Tasks:**
    * Integrate platform-specific In-App Purchase SDKs (StoreKit for iOS, Google Play Billing for Android).
    * Configure the Premium subscription product(s) in App Store Connect and Google Play Console.
    * Implement frontend logic to initiate the purchase flow when the button on F4.5 is tapped.
    * Develop backend logic to securely validate purchase receipts/tokens from Apple/Google.
    * Implement backend logic to update the user's subscription status and expiry date upon successful validation.
    * Implement frontend logic to refresh user status and unlock premium features after successful purchase.
    * Implement error handling for purchase failures or cancellations.
    * Implement logic to handle subscription renewals and expirations (via backend validation/webhooks).
    * Write tests for the entire purchase flow, including success, failure, and status updates.

### Feature: Settings & Notifications

**ID:** F5.1
**User Story:** As a user, I want a Settings screen, so that I can access options to manage my account, preferences, and view legal information.
**Priority:** MVP
**Dependencies:** F1.10 (Logout), F5.3 (Change Password - Post-MVP), F5.4 (Invite Code - Post-MVP), F5.5 (Legal Links), F5.6 (App Version)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am logged in WHEN I navigate through the app THEN I can find and access a "Settings" or "Account" section (e.g., via a profile tab or menu).
    2. GIVEN I am on the Settings screen WHEN I view it THEN I see distinct sections or options for account management (like Logout, potentially Edit Profile link).
    3. GIVEN I am on the Settings screen THEN I see options related to preferences (like Notifications - F5.2, Account Visibility - F5.2).
    4. GIVEN I am on the Settings screen THEN I see options for viewing legal documents (F5.5) and the app version (F5.6).
**Tasks:**
    * Design UI/UX for the main Settings screen layout.
    * Implement the frontend component for the Settings screen.
    * Implement navigation to the Settings screen.
    * Structure the screen with links/navigation to relevant sub-sections or features (Logout, Edit Profile, Notifications, Legal, etc.).
    * Write tests for navigating to and viewing the basic structure of the Settings screen.
---
**ID:** F5.2
**User Story:** As a user, I want options in Settings to control my Account Visibility and Notification preferences, so that I can manage my privacy and how the app communicates with me.
**Priority:** Post-MVP (Notification prefs might be MVP if basic push/in-app exist) - Let's target Post-MVP for specific controls.
**Dependencies:** F5.1, F3.5 (Notifications)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the Settings screen (F5.1) WHEN I navigate to "Notification Settings" THEN I see toggles/options to enable/disable different types of notifications (e.g., New Matches, New Messages).
    2. GIVEN I change a notification preference WHEN I save the changes THEN the backend updates my preferences, and notification delivery (F3.5) respects these settings.
    3. GIVEN I am on the Settings screen WHEN I navigate to "Account Visibility" or similar THEN I see options to control how my profile is shown (Specific options TBD - e.g., "Pause Account", "Incognito Mode").
    4. GIVEN I change an account visibility setting WHEN I save the changes THEN the backend updates my status, and profile discovery (F2.1) respects this setting.
**Tasks:**
    * Define specific options for Notification Preferences (e.g., New Match, New Message, App Updates).
    * Define specific options for Account Visibility (requires further definition - see PRD Open Issues).
    * Design UI/UX for Notification and Visibility settings screens.
    * Implement frontend components for these settings (toggles, options).
    * Develop backend endpoints to save and retrieve user preferences for notifications and visibility.
    * Integrate notification preference checks into the notification sending logic (F3.5).
    * Integrate visibility checks into the profile fetching logic for matching (F2.1).
    * Write tests for saving and applying notification and visibility settings.
---
**ID:** F5.3
**User Story:** As a user, I want to be able to change my account password from the Settings screen, so that I can maintain account security.
**Priority:** Post-MVP
**Dependencies:** F5.1, F1.4 (Requires email/password auth)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am logged in using email/password WHEN I navigate to Settings (F5.1) THEN I find an option like "Change Password".
    2. GIVEN I tap "Change Password" WHEN prompted THEN I must enter my current password correctly.
    3. GIVEN I have entered the correct current password WHEN prompted THEN I can enter a new strong password and confirm it.
    4. GIVEN I have entered and confirmed a valid new password WHEN I tap "Save" or "Update Password" THEN my account password is updated.
    5. GIVEN I enter the incorrect current password WHEN attempting to change it THEN an error message is displayed, and the password is not changed.
    6. GIVEN the new passwords entered do not match WHEN attempting to save THEN an error message is displayed.
**Tasks:**
    * Design UI/UX for the Change Password flow (current password input, new password input/confirmation).
    * Implement frontend components for the Change Password screen.
    * Develop backend endpoint to handle password change requests, including current password verification and new password update.
    * Implement secure password hashing for the new password.
    * Implement password strength validation.
    * Write tests for changing password successfully, with incorrect current password, and with mismatching new passwords.
---
**ID:** F5.4
**User Story:** As a user, I want to view my unique Invite Code in the Settings screen, so that I can share it with others (specific functionality TBD).
**Priority:** Post-MVP (Display only, functionality depends on future invite system)
**Dependencies:** F5.1
**Acceptance Criteria / Test Steps:**
    1. GIVEN Invite Codes are implemented WHEN I navigate to the Settings screen (F5.1) THEN I see a section displaying my unique Invite Code.
    2. GIVEN my Invite Code is displayed WHEN I view it THEN it is easily readable and potentially has a "Copy" button next to it.
    3. GIVEN I tap the "Copy" button (if present) WHEN triggered THEN the invite code is copied to my device clipboard.
**Tasks:**
    * Develop backend logic to generate/assign unique invite codes to users (potentially upon account creation or later).
    * Ensure the backend API can retrieve the user's invite code.
    * Add a display area for the Invite Code on the Settings screen UI.
    * Implement frontend logic to fetch and display the code.
    * Implement optional "Copy to Clipboard" functionality.
    * Write tests to verify the invite code is displayed correctly. (Note: Testing the *effect* of the code is out of scope for this story).
---
**ID:** F5.5
**User Story:** As a user, I want access to legal documents (Privacy Policy, Terms of Service, Licenses) from the Settings screen, so that I can review them at any time.
**Priority:** MVP
**Dependencies:** F5.1
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the Settings screen (F5.1) WHEN I look for legal information THEN I find links clearly labeled "Privacy Policy", "Terms of Service", and potentially "Licenses" or "Acknowledgements".
    2. GIVEN I tap on the "Privacy Policy" link WHEN activated THEN the Privacy Policy document is displayed (e.g., in-app webview or browser).
    3. GIVEN I tap on the "Terms of Service" link WHEN activated THEN the Terms of Service document is displayed.
    4. GIVEN I tap on the "Licenses" link (if present) WHEN activated THEN information about open-source licenses used in the app is displayed.
**Tasks:**
    * Add links for Privacy Policy, Terms of Service, and Licenses to the Settings screen UI.
    * Finalize and host the legal documents at accessible URLs.
    * Implement logic to open these links (e.g., using an in-app browser/webview).
    * Compile list of open-source licenses for the Licenses section.
    * Write tests to verify the links exist and attempt to open the corresponding documents.
---
**ID:** F5.6
**User Story:** As a user, I want to view the app version number in the Settings screen, so that I can reference it for support or troubleshooting.
**Priority:** MVP
**Dependencies:** F5.1
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am on the Settings screen (F5.1) WHEN I scroll to the bottom or look in an "About" section THEN I see the application's version number displayed (e.g., "Version 1.0.0").
**Tasks:**
    * Implement logic to retrieve the app's current version number from the build configuration.
    * Add a text label/display area for the version number on the Settings screen UI.
    * Ensure the version number is dynamically displayed based on the installed build.
    * Write tests to verify the version number is displayed.
---
**ID:** F5.7
**User Story:** As a user, I want a notification center listing recent activity like new matches and new messages, so that I have a central place to catch up on important events.
**Priority:** Post-MVP
**Dependencies:** F2.4 (Matches), F3.4 (Messages), F3.5 (Notifications)
**Acceptance Criteria / Test Steps:**
    1. GIVEN I am logged in WHEN I view the main interface THEN I see a distinct "Notifications" tab or access point (e.g., a bell icon).
    2. GIVEN I have received new matches or messages WHEN I navigate to the Notification Center THEN I see a list of recent activities chronologically (newest first).
    3. GIVEN the list displays notifications WHEN I view an entry for a new match THEN it shows the matched user's name/picture and a timestamp.
    4. GIVEN the list displays notifications WHEN I view an entry for a new message THEN it shows the sender's name/picture, a message snippet, and a timestamp.
    5. GIVEN I tap on a "New Match" notification WHEN activated THEN I am navigated to the profile of the matched user or the newly created chat screen.
    6. GIVEN I tap on a "New Message" notification WHEN activated THEN I am navigated to the corresponding chat screen (F3.4).
    7. GIVEN the Notification Center displays items WHEN I view them THEN unread notifications might be visually distinct (e.g., background color, dot) and potentially marked as read upon viewing the center or tapping the item.
**Tasks:**
    * Design UI/UX for the Notification Center screen and list items.
    * Add navigation access to the Notification Center.
    * Develop backend logic/data model to store notification events (match, message) per user.
    * Develop backend endpoint to fetch the user's notification list.
    * Implement frontend logic to fetch and display notifications chronologically.
    * Implement differentiation for notification types (match vs. message).
    * Implement navigation logic when tapping on notifications.
    * Implement read/unread status management for notifications.
    * Write tests for fetching, displaying, and interacting with notifications in the center.
