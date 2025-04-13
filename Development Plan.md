# Mockaccino Mobile App - Development Task Plan (v1.0)

This document outlines the development tasks for building the Mockaccino mobile application, derived from PRD v1.0, User Stories v1.0, Brand Guidelines v1.0, Database Schema v1.0, Screen Flows v1.0, and Test Cases v1.0.

---
**Task #1:** Initial Project Setup & Basic Navigation Shell
**Status:** To Do
**Relevant Artifacts:** PRD Sec 1 (Overview), PRD Sec 5 (MVP Scope), Brand Guidelines (General Theme), Screen Flows (Overall Structure)
**AI Coding Prompt:**
"
**Objective:** Initialize the cross-platform mobile application project (e.g., React Native, Flutter) and set up the basic navigation structure (e.g., stack navigator) to handle transitions between the initial screens (Landing, Sign Up, Login).

**Context & Requirements:**
* Establish the core project directories and configuration files.
* Integrate a basic navigation library.
* Define initial navigation routes for Landing, Email Sign Up, and Email Login screens based on the Screen Flows (New User Onboarding, Existing User Login).
* Apply basic theme settings (e.g., primary color) from Brand Guidelines (Sec 3: Color Palette - Primary #0A4D68) if applicable at this stage.

**Action:** Create the initial project structure. Implement a basic navigation container with placeholders for the Landing, Email Sign Up, and Email Login screens. Ensure navigation can be triggered between these placeholders.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Requirements:** Does the project structure follow common conventions for the chosen framework? Is a navigation library integrated?
2.  **Review Test Cases:** N/A for this setup task.
3.  **Validate UI:** Are placeholder screens defined? Can you navigate between the Landing, Sign Up, and Login placeholder screens as per the initial Screen Flows?
4.  **Functionality Check:** Confirm the project builds successfully and the basic navigation shell operates without errors.
5.  **List Assumptions/Issues:** List any framework choices made or potential navigation setup issues.
"
---
**Task #2:** Implement Landing Screen UI
**Status:** To Do
**Relevant Artifacts:** PRD Sec 2 (Feature 1), PRD Page 4 (Mockup Ref), Screen Flows (New User Onboarding - Step 1), Brand Guidelines (Sec 2: Logo, Sec 3: Colors, Sec 4: Typography, Sec 8: Voice/Tone, Sec 9: Capitalization), User Story F1.1, F1.4, F1.12, F1.13 (for button presence)
**AI Coding Prompt:**
"
**Objective:** Implement the user interface for the initial Landing Screen.

**Context & Requirements:**
* Display the Mockaccino logo (Brand Guidelines Sec 2).
* Include buttons/options for "Sign Up with Email", "Log In" (PRD Sec 2, User Stories F1.1, F1.4).
* Include placeholders or buttons for "Sign Up with Apple" and "Sign Up with LinkedIn" (Post-MVP, F1.12, F1.13 - ensure they are styled but potentially disabled/marked for future implementation).
* Adhere to visual design from UI PDF Page 4 (Reference).
* Use Brand Guidelines: Primary Color (#0A4D68) for main action buttons, Secondary Color (#F5F5F5) for background/alternative actions, Primary Font (Inter) for text, appropriate font sizes/weights (Sec 4), button capitalization (Sentence case, Sec 9).

**Action:** Create the UI component for the Landing Screen. Implement the layout, logo display, and buttons as specified. Connect button taps to navigate to the respective (placeholder) screens defined in Task #1.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** N/A directly, but supports initiation of F1.1/F1.4 flows.
2.  **Review Test Cases:** Does the screen layout support the preconditions for TC_F1.1_01 and TC_F1.4_01 (presence of respective buttons)?
3.  **Validate UI:** Does the UI match the Mockup (Page 4)? Does it adhere to Brand Guidelines (Logo Usage, Colors: #0A4D68, #F5F5F5, #FFFFFF, #495057, Typography: Inter, Button Styling, Spacing)?
4.  **Functionality Check:** Do the "Sign Up with Email" and "Log In" buttons navigate to the correct (placeholder) screens? Are the Post-MVP buttons present and visually distinct/disabled?
5.  **List Assumptions/Issues:** List any assumptions made about layout details not specified or potential UI framework limitations.
"
---
**Task #3:** Implement Email Sign Up Screen UI
**Status:** To Do
**Relevant Artifacts:** User Story F1.1, F1.2, PRD Page 5 (Mockup Ref), Screen Flows (New User Onboarding - Step 2), Brand Guidelines (Sec 3: Colors, Sec 4: Typography, Sec 5: UI Elements, Sec 9: Capitalization), Test Cases (TC_F1.1_01, TC_F1.1_02, TC_F1.1_05, TC_F1.1_06, TC_F1.1_07)
**AI Coding Prompt:**
"
**Objective:** Implement the user interface for the Email Sign Up screen.

**Context & Requirements:**
* Implement input fields for Full Name, Email, City, Password, and Confirm Password (User Story F1.1).
* Include a placeholder for Profile Picture upload (User Story F1.2).
* Include a checkbox for accepting Terms of Service, with links to Terms/Privacy Policy (User Story F1.1, Screen Flow Step 2).
* Include a "Sign Up" button, initially disabled (User Story F1.1 AC 2).
* Display inline validation error messages near relevant fields (User Story F1.1 AC 5, 6).
* Adhere to visual design from UI PDF Page 5 (Reference).
* Use Brand Guidelines: Primary Color (#0A4D68) for the Sign Up button, standard input field styling (Sec 5), error message styling (e.g., using Accent Red #DC3545, Sec 3), Primary Font (Inter) for labels/inputs (Sec 4), appropriate capitalization (Sec 9).

**Action:** Create the UI component for the Email Sign Up Screen. Implement the layout, input fields, profile picture placeholder, checkbox, links, button, and areas for validation messages. Ensure the "Sign Up" button starts disabled.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the UI contain all elements required by User Story F1.1 AC 1 & 2 and F1.2 (placeholder)?
2.  **Review Test Cases:** Does the UI layout support TC_F1.1_01 (presence of fields), TC_F1.1_02 (initially disabled button), TC_F1.1_05 (space for inline email error), TC_F1.1_06 (space for password mismatch error), TC_F1.1_07 (presence of checkbox)?
3.  **Validate UI:** Does the UI match the Mockup (Page 5)? Does it adhere to Brand Guidelines (Colors: #0A4D68, #F5F5F5, #495057, #DC3545, Typography: Inter, Input Styling, Button Styling, Spacing)?
4.  **Functionality Check:** Is the "Sign Up" button initially disabled? Are the Terms/Privacy links present (non-functional is okay for this task)?
5.  **List Assumptions/Issues:** List any assumptions about specific spacing, error message placement, or link handling.
"
---
**Task #4:** Implement Email Sign Up Client-Side Logic & Basic Validation
**Status:** To Do
**Relevant Artifacts:** User Story F1.1, Test Cases (TC_F1.1_02, TC_F1.1_05, TC_F1.1_06, TC_F1.1_07), Screen Flows (New User Onboarding - Step 2), PRD Sec 2.1.1 (Password Rules)
**AI Coding Prompt:**
"
**Objective:** Implement the client-side logic for the Email Sign Up screen, including input handling, basic validation, and enabling/disabling the Sign Up button.

**Context & Requirements:**
* Enable the "Sign Up" button only when Full Name, Email, City, Password, Confirm Password are non-empty, passwords match, password meets strength requirements, and the Terms checkbox is checked (User Story F1.1 AC 2).
* Implement inline validation for email format (User Story F1.1 AC 5). Show an error message if invalid.
* Implement validation check for password match when the "Sign Up" button is tapped (or potentially on field blur) (User Story F1.1 AC 6). Show an error message if they don't match.
* Implement check for Terms acceptance when the "Sign Up" button is tapped (User Story F1.1 AC 7). Show an error message if not checked.
* Password strength rules (PRD Sec 2.1.1 - min 8 chars, mix case/number/symbol) should be validated. Show an error if rules aren't met.

**Action:** Add state management to the Email Sign Up component to track input values and validation status. Implement the validation functions (email format, password match, terms checked, password strength). Update the component to display validation errors and conditionally enable the "Sign Up" button based on the validation state.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the logic correctly enable the button based on F1.1 AC 2? Does it implement validation checks for F1.1 AC 5, 6, 7 and password strength (PRD Sec 2.1.1)?
2.  **Review Test Cases:** Does the logic correctly handle scenarios described in TC_F1.1_02 (button enabling), TC_F1.1_05 (email validation), TC_F1.1_06 (password mismatch), TC_F1.1_07 (terms checkbox)? Does it check password strength?
3.  **Validate UI:** Do validation error messages appear correctly as per the UI design (Task #3) when validation fails? Does the button enable/disable state change correctly?
4.  **Functionality Check:** Perform a mental walk-through: Enter valid data -> button enables. Enter invalid email -> error shows, button disables. Enter mismatching passwords -> error shows, button disables. Uncheck terms -> button disables. Enter weak password -> error shows, button disables.
5.  **List Assumptions/Issues:** List any assumptions about when validation triggers (on blur vs. on submit) or specific error message text if not provided.
"
---
**Task #5:** Implement Email Sign Up Backend Interaction (Account Creation)
**Status:** To Do
**Relevant Artifacts:** User Story F1.1, Database Schema (`users` collection), Screen Flows (New User Onboarding - Step 2 -> 3), Test Cases (TC_F1.1_03, TC_F1.1_04)
**AI Coding Prompt:**
"
**Objective:** Implement the backend interaction logic for creating a new user account when the "Sign Up" button is tapped with valid data.

**Context & Requirements:**
* When the "Sign Up" button is tapped and client-side validation passes:
    * Call the backend authentication service to create a user with the provided email and password.
    * Handle potential errors from the backend, such as "Email already exists" (User Story F1.1 AC 4). Display an appropriate error message to the user.
    * If authentication is successful, save the user's profile data (Full Name, Email, City, Auth Provider='email', initial empty/default values for other required fields) to the `users` collection in the database, using the Auth UID as the Document ID (Database Schema: `users`).
    * Upon successful account creation and profile save, log the user in automatically and navigate them to the next step in the onboarding flow (Select Role screen - F1.6 placeholder for now) (User Story F1.1 AC 3, Screen Flow Step 2 -> 3).

**Action:** Implement the function triggered by the "Sign Up" button tap. This function should:
    1. Perform final client-side validation checks (redundancy is good).
    2. Call the authentication service API (e.g., Firebase Auth `createUserWithEmailAndPassword`).
    3. Handle the response:
        * On success: Extract the User ID (UID). Call a backend function or directly write to the database (`users` collection) to store `fullName`, `email`, `city`, `authProvider`='email', `userId`=UID, `createdAt`=Timestamp.now(), `profilePhotoUrl`=null, `interactionPreference`=null, `currentRole`=null, `targetRoles`=[], `skills`=[], `bio`="", `linkedInUrl`="", `availabilitySchedule`={}, `accountStatus`='active', `isPremium`=false, `lastActive`=Timestamp.now(), `notificationSettings`={/* default settings */}, `accountVisibility`='visible'. Navigate to the 'Select Role' screen placeholder.
        * On failure (e.g., email exists): Display the specific error message (F1.1 AC 4).

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the logic attempt account creation (F1.1 AC 3)? Does it handle the "Email already exists" error (F1.1 AC 4)? Does it save the required initial data to the `users` collection (Schema)? Does it navigate on success (F1.1 AC 3)?
2.  **Review Test Cases:** Does the logic cover the success scenario in TC_F1.1_03 (account created, logged in, navigated)? Does it cover the failure scenario in TC_F1.1_04 (email exists error)?
3.  **Validate UI:** Does the appropriate error message display on failure? Is there a visual indicator (e.g., loading spinner) during the backend call? Does navigation occur on success?
4.  **Functionality Check:** Describe the flow: Valid data -> Tap Sign Up -> Auth call -> DB write -> Navigation. Invalid data (existing email) -> Tap Sign Up -> Auth call -> Error display. Check that all required fields in the `users` schema are populated with initial/default values.
5.  **List Assumptions/Issues:** List any assumptions about the specific APIs of the auth/database services, default notification settings, or error handling details. Assume navigation target 'Select Role' screen exists as a placeholder.
"
---
**Task #6:** Implement Profile Picture Upload UI & Logic
**Status:** To Do
**Relevant Artifacts:** User Story F1.2, PRD Page 5 (Mockup Ref - Sign Up), PRD Page 9 (Mockup Ref - Edit Profile), Database Schema (`users.profilePhotoUrl`), Test Cases (TC_F1.2_01, TC_F1.2_02, TC_F1.2_03)
**AI Coding Prompt:**
"
**Objective:** Implement the functionality for users to upload a profile picture during sign-up (optional) and later via profile editing.

**Context & Requirements:**
* On the Email Sign Up screen (Task #3) and Edit Profile screen (future task), provide a way to trigger image selection (e.g., tapping a placeholder/current image) (User Story F1.2 AC 1).
* Allow the user to choose an image from their device's gallery or take a new photo using the camera (User Story F1.2 AC 1).
* Display the selected image as a preview on the screen (User Story F1.2 AC 2).
* Implement image upload to a storage service (e.g., Firebase Storage).
* On successful upload, store the public URL of the uploaded image in the `profilePhotoUrl` field of the corresponding user's document in the `users` collection (User Story F1.2 AC 3, Database Schema).
* Handle potential errors during image selection or upload (e.g., permissions denied, upload failure) and provide feedback to the user.

**Action:**
1.  Add an image picker component/library to the project.
2.  Modify the Email Sign Up screen UI (Task #3) and create a similar component for the Edit Profile screen (placeholder for now) to include a tappable area for the profile picture.
3.  Implement the logic to request necessary permissions (camera, gallery).
4.  Implement the image selection flow (launching gallery/camera).
5.  Implement the image upload function to the designated storage bucket. Use the `userId` to create a unique path (e.g., `profilePictures/{userId}.jpg`).
6.  On successful upload, get the download URL.
7.  Update the `profilePhotoUrl` field in the user's Firestore document. This might happen immediately on upload during Edit Profile, or as part of the main Sign Up action (Task #5). Clarify timing. For now, assume immediate update on successful upload.
8.  Update the UI to display the newly uploaded image.
9.  Add error handling and user feedback for permission issues or upload failures.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the implementation allow choosing/taking a photo (F1.2 AC 1)? Does it display the selected image preview (F1.2 AC 2)? Does it upload and save the URL to `users.profilePhotoUrl` (F1.2 AC 3)?
2.  **Review Test Cases:** Does the logic cover TC_F1.2_01 (triggering selection), TC_F1.2_02 (previewing image), and TC_F1.2_03 (successful upload and URL save)? Does it handle potential permission errors?
3.  **Validate UI:** Does the image placeholder change to the selected/uploaded image? Are error messages displayed appropriately?
4.  **Functionality Check:** Walk through the process: Tap placeholder -> Choose image -> Image displays -> Image uploads -> URL saved in DB. Check error handling for permissions/upload failures. Confirm timing of DB update.
5.  **List Assumptions/Issues:** List assumptions about image compression/resizing, storage bucket rules, specific library usage, and timing of the database update for the photo URL.
"
---
**Task #7:** Implement Select Role Screen UI & Logic (Onboarding Step)
**Status:** To Do
**Relevant Artifacts:** User Story F1.6, PRD Page 6 (Mockup Ref), Screen Flows (New User Onboarding - Step 3), Database Schema (`users.currentRole`, `users.targetRoles`), Test Cases (TC_F1.6_01, TC_F1.6_02, TC_F1.6_03), PRD Sec 8 (Role source question)
**AI Coding Prompt:**
"
**Objective:** Implement the 'Select Role' screen, allowing new users to specify their current role and target roles as part of the onboarding flow.

**Context & Requirements:**
* This screen appears after successful sign-up (Task #5).
* Display input fields or searchable dropdowns/pickers for "Current Role" and "Target Role(s)" (User Story F1.6 AC 1). Assume a basic predefined list of roles is available for MVP (addressing PRD Sec 8 question for now).
* Allow selection of one "Current Role".
* Allow selection of one or more "Target Role(s)" (User Story F1.6 AC 2).
* Include a "Next" or "Continue" button, enabled only after at least a Current Role is selected (User Story F1.6 AC 3).
* Adhere to visual design from UI PDF Page 6 (Reference).
* Use Brand Guidelines (Sec 3: Colors, Sec 4: Typography, Sec 5: UI Elements).
* On tapping "Next", save the selected role(s) to the user's document in the `users` collection (`currentRole`, `targetRoles` fields) (User Story F1.6 AC 4, Database Schema).
* Navigate to the next onboarding step (Select Interaction Preference - F1.7 placeholder) (User Story F1.6 AC 4, Screen Flow Step 3 -> 4).

**Action:**
1.  Create the UI component for the 'Select Role' screen.
2.  Implement UI elements for selecting/inputting Current Role and Target Role(s). Use appropriate pickers or input fields based on the predefined list assumption.
3.  Implement logic to manage selected roles and enable the "Next" button based on selection criteria.
4.  Implement the action for the "Next" button: Update the user's document in Firestore with `currentRole` and `targetRoles`.
5.  Navigate to the 'Select Interaction Preference' screen placeholder upon successful save.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the UI allow selecting current/target roles (F1.6 AC 1, 2)? Is the "Next" button enabled correctly (F1.6 AC 3)? Does tapping "Next" save data and navigate (F1.6 AC 4)?
2.  **Review Test Cases:** Does the implementation cover TC_F1.6_01 (selecting roles), TC_F1.6_02 (enabling Next button), and TC_F1.6_03 (saving data and navigating)?
3.  **Validate UI:** Does the UI match the Mockup (Page 6)? Does it adhere to Brand Guidelines (Colors, Typography, UI Elements)?
4.  **Functionality Check:** Walk through: Select Current Role -> Button enables -> Select Target Role(s) -> Tap Next -> Data saved to `users.currentRole`, `users.targetRoles` -> Navigation occurs. Check edge cases like selecting/deselecting roles.
5.  **List Assumptions/Issues:** List assumptions about the source/format of the role list (confirming predefined for MVP), UI component choice for selection, and the exact name of the next navigation target screen.
"
---
**Task #8:** Implement Select Interaction Preference Screen UI & Logic (Onboarding Step)
**Status:** To Do
**Relevant Artifacts:** User Story F1.7, PRD Page 7 (Mockup Ref), Screen Flows (New User Onboarding - Step 4), Database Schema (`users.interactionPreference`), Test Cases (TC_F1.7_01, TC_F1.7_02, TC_F1.7_03)
**AI Coding Prompt:**
"
**Objective:** Implement the 'Select Interaction Preference' screen, allowing new users to choose their primary goal on the app (Mock Interview, Referral Exchange, or Both) during onboarding.

**Context & Requirements:**
* This screen appears after the 'Select Role' screen (Task #7).
* Present clear options for "Mock Interview", "Referral Exchange", and "Both" (User Story F1.7 AC 1). Use radio buttons, toggle buttons, or similar selection controls.
* Allow selection of only one preference (Mock Interview, Referral Exchange, or Both).
* Include a "Finish" or "Complete Profile" button, enabled only after a preference is selected (User Story F1.7 AC 2).
* Adhere to visual design from UI PDF Page 7 (Reference).
* Use Brand Guidelines (Sec 3: Colors, Sec 4: Typography, Sec 5: UI Elements).
* On tapping "Finish", save the selected preference to the user's document in the `users` collection (`interactionPreference` field) (User Story F1.7 AC 3, Database Schema).
* Navigate to the main application interface (e.g., Matching/Home screen placeholder) (User Story F1.7 AC 3, Screen Flow Step 4 -> 5).

**Action:**
1.  Create the UI component for the 'Select Interaction Preference' screen.
2.  Implement UI elements for selecting the interaction preference.
3.  Implement logic to manage the selected preference and enable the "Finish" button.
4.  Implement the action for the "Finish" button: Update the user's document in Firestore with `interactionPreference`.
5.  Navigate to the main app screen placeholder (e.g., 'Home' or 'Matching') upon successful save.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the UI present the options clearly (F1.7 AC 1)? Is the "Finish" button enabled correctly (F1.7 AC 2)? Does tapping "Finish" save the preference and navigate to the main app (F1.7 AC 3)?
2.  **Review Test Cases:** Does the implementation cover TC_F1.7_01 (selecting preference), TC_F1.7_02 (enabling Finish button), and TC_F1.7_03 (saving data and navigating)?
3.  **Validate UI:** Does the UI match the Mockup (Page 7)? Does it adhere to Brand Guidelines (Colors, Typography, UI Elements)?
4.  **Functionality Check:** Walk through: Select a preference -> Button enables -> Tap Finish -> Data saved to `users.interactionPreference` -> Navigation to main app occurs. Check that only one option can be selected.
5.  **List Assumptions/Issues:** List assumptions about the exact wording of options, UI component choice for selection, and the name of the main app navigation target.
"
---
**Task #9:** Implement Email Login Screen UI & Logic
**Status:** To Do
**Relevant Artifacts:** User Story F1.4, PRD Page 8 (Mockup Ref), Screen Flows (Existing User Login - Step 1 & 2), Brand Guidelines (Sec 3: Colors, Sec 4: Typography, Sec 5: UI Elements), Test Cases (TC_F1.4_01, TC_F1.4_02, TC_F1.4_03, TC_F1.4_04)
**AI Coding Prompt:**
"
**Objective:** Implement the UI and client-side logic for the Email Login screen.

**Context & Requirements:**
* Provide input fields for Email and Password (User Story F1.4 AC 1).
* Include a "Log In" button (User Story F1.4 AC 1).
* Include a "Forgot Password?" link (User Story F1.4 AC 4).
* Adhere to visual design from UI PDF Page 8 (Reference).
* Use Brand Guidelines (Colors, Typography, Input Styling, Button Styling).
* Implement basic client-side validation (e.g., check if fields are non-empty).
* When "Log In" is tapped:
    * Perform client-side validation.
    * Call the backend authentication service to sign the user in with email and password.
    * Handle successful login: Navigate to the main application screen (e.g., Matching/Home) (User Story F1.4 AC 2). Update `lastActive` timestamp in user's DB record.
    * Handle login failures (e.g., wrong password, user not found): Display an appropriate error message (User Story F1.4 AC 3).
* When "Forgot Password?" is tapped: Navigate to the Password Reset Request screen (F1.5 placeholder) (User Story F1.4 AC 4).

**Action:**
1.  Create the UI component for the Email Login screen with Email/Password fields, Log In button, and Forgot Password link.
2.  Implement state management for input fields.
3.  Implement the login function triggered by the "Log In" button:
    * Validate inputs.
    * Call the authentication service API (e.g., Firebase Auth `signInWithEmailAndPassword`).
    * Handle success: Update `lastActive` timestamp in Firestore `users` document. Navigate to the main app screen.
    * Handle failure: Display error message.
4.  Implement navigation to the 'Password Reset Request' screen placeholder when the "Forgot Password?" link is tapped.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the UI have the required fields/button/link (F1.4 AC 1, 4)? Does successful login navigate to the main app (F1.4 AC 2)? Are login errors handled (F1.4 AC 3)? Does the forgot password link navigate (F1.4 AC 4)? Is `lastActive` updated on successful login?
2.  **Review Test Cases:** Does the implementation cover TC_F1.4_01 (UI elements), TC_F1.4_02 (successful login/navigation/timestamp update), TC_F1.4_03 (failed login/error message), and TC_F1.4_04 (forgot password navigation)?
3.  **Validate UI:** Does the UI match the Mockup (Page 8)? Does it adhere to Brand Guidelines? Are error messages displayed correctly?
4.  **Functionality Check:** Walk through: Enter valid credentials -> Tap Log In -> Auth call -> DB update (`lastActive`) -> Navigation. Enter invalid credentials -> Tap Log In -> Auth call -> Error display. Tap Forgot Password -> Navigation.
5.  **List Assumptions/Issues:** List assumptions about specific error messages, auth API details, and navigation target names.
"
---
**Task #10:** Implement Forgot Password Flow UI & Logic (Request & Reset)
**Status:** To Do
**Relevant Artifacts:** User Story F1.5, Screen Flows (Password Reset Flow), Brand Guidelines (Sec 3: Colors, Sec 4: Typography, Sec 5: UI Elements), Test Cases (TC_F1.5_01, TC_F1.5_02, TC_F1.5_03, TC_F1.5_04, TC_F1.5_05), PRD Sec 2.1.1 (Password Rules)
**AI Coding Prompt:**
"
**Objective:** Implement the UI and logic for the Forgot Password flow, including requesting a password reset email and handling the reset itself (potentially via deep link).

**Context & Requirements:**
* **Password Reset Request Screen:**
    * Accessed from the Login screen (Task #9).
    * Contains an input field for the user's email address (User Story F1.5 AC 1).
    * Includes a "Send Reset Link" button (User Story F1.5 AC 1).
    * On button tap: Call backend auth service to send a password reset email to the entered address (User Story F1.5 AC 2).
    * Display a confirmation message on success (e.g., "Password reset email sent") (User Story F1.5 AC 2).
    * Handle errors (e.g., email not found) and display an error message (User Story F1.5 AC 3).
* **Password Reset Screen (Handling the link):**
    * Needs to handle being opened via a deep link from the reset email.
    * Contains fields for New Password and Confirm New Password.
    * Includes a "Reset Password" button.
    * On button tap: Validate passwords match and meet strength requirements (PRD Sec 2.1.1). Call backend auth service to confirm the password reset using the code from the deep link and the new password (User Story F1.5 AC 4).
    * Display success message and navigate to Login screen on success (User Story F1.5 AC 4).
    * Display error messages for invalid code, weak password, or mismatch (User Story F1.5 AC 5).
* Adhere to Brand Guidelines for UI elements.

**Action:**
1.  Create the UI component for the 'Password Reset Request' screen. Implement the email input and button. Implement the logic to call the auth service's `sendPasswordResetEmail` (or equivalent) function and handle success/error feedback.
2.  Configure deep linking in the app to handle the password reset URL.
3.  Create the UI component for the 'Password Reset' screen (handling the link). Implement password input fields and the reset button.
4.  Implement the logic to extract the reset code from the deep link, validate new passwords (match and strength), call the auth service's `confirmPasswordReset` (or equivalent) function, and handle success/error feedback and navigation.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Can the user request a reset email (F1.5 AC 1, 2)? Are errors handled (F1.5 AC 3)? Can the user reset the password via the link/screen (F1.5 AC 4)? Are reset errors handled (F1.5 AC 5)? Is password strength checked on reset (PRD Sec 2.1.1)?
2.  **Review Test Cases:** Does the implementation cover TC_F1.5_01 (Request UI), TC_F1.5_02 (Request success), TC_F1.5_03 (Request failure), TC_F1.5_04 (Reset success), TC_F1.5_05 (Reset failure)?
3.  **Validate UI:** Do the screens adhere to Brand Guidelines? Are confirmation/error messages displayed clearly?
4.  **Functionality Check:** Walk through: Request reset -> Check confirmation/error. Simulate clicking link -> Enter new passwords -> Check success/error/navigation. Check password strength/match validation on the reset screen.
5.  **List Assumptions/Issues:** List assumptions about auth service API details, deep link configuration specifics, and exact confirmation/error message wording.
"
---
**Task #11:** Implement Main Navigation (e.g., Tab Bar)
**Status:** To Do
**Relevant Artifacts:** PRD Sec 5.1 (MVP Features - implies navigation between core areas), Brand Guidelines (Sec 5: UI Elements - Navigation)
**AI Coding Prompt:**
"
**Objective:** Implement the main application navigation structure, likely a bottom tab bar, providing access to the core MVP feature areas.

**Context & Requirements:**
* Once a user is logged in (after Sign Up/Login), they should see the main app interface.
* Implement a primary navigation method (e.g., bottom tab bar) as suggested by common mobile patterns and potentially implied by mockups (if available).
* The navigation should include access points (tabs) for:
    * Matching / Home (User Story F2.1)
    * Connections / Chat List (User Story F3.1)
    * Notifications (User Story F5.7)
    * Profile (User Story F1.8)
* Use appropriate icons and labels for each tab, adhering to Brand Guidelines (Sec 5: Icons, Sec 4: Typography).
* Ensure the navigation persists across these main sections.
* Implement placeholder screens for each section initially if the target screens are not yet built.

**Action:**
1.  Integrate a tab navigation container within the main application structure (after the authentication flow).
2.  Define the tabs (Matching, Connections, Notifications, Profile) with appropriate labels and icons.
3.  Link each tab to its corresponding screen (or placeholder screen).
4.  Style the tab bar according to Brand Guidelines (colors, active/inactive states).

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Requirements:** Is a main navigation structure (e.g., tab bar) implemented? Does it include tabs for Matching, Connections, Notifications, and Profile?
2.  **Review Test Cases:** N/A directly, but enables preconditions for tests involving navigating between main sections (e.g., TC_F1.8_01, TC_F3.1_01, TC_F5.7_01).
3.  **Validate UI:** Is the tab bar visible on the main app screens? Do the icons and labels adhere to Brand Guidelines? Does the active tab indicator work correctly?
4.  **Functionality Check:** Can the user tap on each tab to navigate to the corresponding section (or placeholder)? Does the navigation feel smooth and standard?
5.  **List Assumptions/Issues:** List assumptions about the specific type of navigation (tab bar confirmed?), icon choices if not specified, and exact labels.
"
---
**Task #12:** Implement Profile Screen UI (Displaying User Data)
**Status:** To Do
**Relevant Artifacts:** User Story F1.8, PRD Page 9 (Mockup Ref), Database Schema (`users` collection), Brand Guidelines (Sec 3: Colors, Sec 4: Typography, Sec 5: UI Elements), Test Cases (TC_F1.8_01)
**AI Coding Prompt:**
"
**Objective:** Implement the user interface for the Profile screen, displaying the logged-in user's information.

**Context & Requirements:**
* The Profile screen should be accessible via the main navigation (Task #11).
* Display the user's profile picture (if available), full name, city, current role, target roles, interaction preference, and bio (User Story F1.8 AC 1, referencing fields from `users` schema).
* Include an "Edit Profile" button/icon to navigate to the profile editing screen (User Story F1.8 AC 2, F1.9).
* Include access to Account Settings (e.g., a gear icon or menu item) (User Story F1.11).
* Include a "Logout" button/option (User Story F1.10).
* Adhere to visual design from UI PDF Page 9 (Reference).
* Use Brand Guidelines for layout, typography, colors, and element styling.

**Action:**
1.  Create the UI component for the Profile Screen.
2.  Implement the layout to display the user's profile picture, name, city, roles, preference, and bio. Fetch this data from the logged-in user's state or database record.
3.  Add the "Edit Profile" button/icon and link it to navigate to the (placeholder) Edit Profile screen.
4.  Add the Account Settings entry point and link it to the (placeholder) Account Settings screen.
5.  Add the "Logout" button/option.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the screen display the required profile information (F1.8 AC 1)? Does it include Edit, Settings, and Logout options (F1.8 AC 2, F1.11, F1.10)?
2.  **Review Test Cases:** Does the UI layout support TC_F1.8_01 (displaying profile info and edit button)?
3.  **Validate UI:** Does the UI match the Mockup (Page 9)? Does it adhere to Brand Guidelines (Colors, Typography, Spacing, Element Styling)? Is data displayed correctly (e.g., profile picture)?
4.  **Functionality Check:** Does the screen load and display user data correctly? Do the Edit, Settings, and Logout buttons/links exist (navigation can be placeholder)?
5.  **List Assumptions/Issues:** List assumptions about how data is fetched/passed to the screen, specific layout details if mockup is unclear, and exact wording/icons for buttons.
"
---
**Task #13:** Implement Edit Profile Screen UI
**Status:** To Do
**Relevant Artifacts:** User Story F1.9, PRD Page 9 (Mockup Ref - implies editable fields), Database Schema (`users` collection - fields to edit), Brand Guidelines (Sec 3: Colors, Sec 4: Typography, Sec 5: UI Elements), Test Cases (TC_F1.9_01)
**AI Coding Prompt:**
"
**Objective:** Implement the user interface for the Edit Profile screen, allowing users to modify their profile information.

**Context & Requirements:**
* The Edit Profile screen is accessed from the Profile screen (Task #12).
* Provide editable fields/controls for:
    * Profile Picture (linking to upload logic from Task #6) (User Story F1.2)
    * Full Name
    * City
    * Current Role (using selection method from Task #7)
    * Target Role(s) (using selection method from Task #7)
    * Bio (multiline text input)
    * LinkedIn Profile URL (optional field)
    * Skills (placeholder for future implementation/Post-MVP)
    * Availability Schedule (placeholder for future implementation/Post-MVP)
    (User Story F1.9 AC 1, referencing `users` schema fields)
* Include a "Save" or "Update" button to submit changes.
* Include a "Cancel" or Back navigation mechanism.
* Adhere to visual design implied by UI PDF Page 9 (Reference) or standard edit form patterns.
* Use Brand Guidelines for layout, typography, colors, and element styling (inputs, buttons).

**Action:**
1.  Create the UI component for the Edit Profile Screen.
2.  Populate the screen with the user's current profile data loaded into editable input fields/controls.
3.  Integrate the profile picture update mechanism (Task #6).
4.  Implement controls for editing name, city, roles (reuse role selection UI), bio, and LinkedIn URL.
5.  Add placeholders for Skills and Availability.
6.  Add "Save" and "Cancel"/Back buttons/navigation.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the screen provide editable controls for the specified fields (F1.9 AC 1)? Does it include a Save mechanism?
2.  **Review Test Cases:** Does the UI layout support TC_F1.9_01 (presence of editable fields and Save button)?
3.  **Validate UI:** Does the UI generally match the implied design from Mockup (Page 9) or follow standard editing patterns? Does it adhere to Brand Guidelines (Input Styling, Button Styling, etc.)? Are current user values pre-filled?
4.  **Functionality Check:** Does the screen load with current data? Are the input fields editable? Are Save/Cancel buttons present?
5.  **List Assumptions/Issues:** List assumptions about specific UI controls used (e.g., text input vs. picker), handling of optional fields, and placeholder appearance.
"
---
**Task #14:** Implement Edit Profile Logic (Saving Changes)
**Status:** To Do
**Relevant Artifacts:** User Story F1.9, Database Schema (`users` collection), Test Cases (TC_F1.9_02, TC_F1.9_03)
**AI Coding Prompt:**
"
**Objective:** Implement the logic to save the user's changes made on the Edit Profile screen to the database.

**Context & Requirements:**
* When the user taps the "Save" button on the Edit Profile screen (Task #13):
    * Collect the updated values from all editable fields (Name, City, Roles, Bio, LinkedIn URL, potentially Profile Picture URL if updated via Task #6).
    * Perform any necessary client-side validation (e.g., ensure required fields like Name are not empty).
    * Update the user's document in the `users` collection in Firestore with the modified fields (User Story F1.9 AC 2).
    * Handle potential errors during the save operation and provide feedback to the user (User Story F1.9 AC 3).
    * On successful save, navigate the user back to the Profile screen (Task #12), which should now display the updated information (User Story F1.9 AC 2).
    * If the user cancels or navigates back, changes should not be saved.

**Action:**
1.  Implement state management for the Edit Profile screen to track changes.
2.  Implement the "Save" button action:
    * Retrieve current values from the state/inputs.
    * Perform validation.
    * Call the database service to update the relevant fields in the `users` document for the logged-in user. Use `update` rather than `set` to only change modified fields.
    * Handle success: Navigate back to the Profile screen. Show a success indicator (e.g., toast message).
    * Handle failure: Display an error message to the user. Stay on the Edit Profile screen.
3.  Ensure the Cancel/Back action discards changes and navigates back.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does tapping Save attempt to update the DB with changed values (F1.9 AC 2)? Does it navigate back on success (F1.9 AC 2)? Are save errors handled (F1.9 AC 3)?
2.  **Review Test Cases:** Does the logic cover TC_F1.9_02 (successful save and navigation)? Does it cover TC_F1.9_03 (save failure and error message)?
3.  **Validate UI:** Is user feedback provided on success (navigation, optional toast)? Is an error message shown on failure?
4.  **Functionality Check:** Walk through: Change data -> Tap Save -> DB update call -> Success feedback & navigation OR Error feedback. Tap Cancel/Back -> No DB update -> Navigation. Verify only changed fields are sent in the update operation.
5.  **List Assumptions/Issues:** List assumptions about specific validation rules, error message content, and success feedback mechanism.
"
---
**Task #15:** Implement Matching Screen UI (Basic Card View)
**Status:** To Do
**Relevant Artifacts:** User Story F2.1, PRD Page 10 (Mockup Ref), Brand Guidelines (Sec 3: Colors, Sec 4: Typography, Sec 5: UI Elements), Test Cases (TC_F2.1_01)
**AI Coding Prompt:**
"
**Objective:** Implement the basic user interface for the main Matching screen, displaying potential matches as interactive cards.

**Context & Requirements:**
* This screen is a primary tab in the main navigation (Task #11).
* Display potential matches one at a time in a card format (User Story F2.1 AC 1).
* Each card should display key information about the potential match:
    * Profile Picture
    * Full Name
    * City
    * Current Role
    * Target Role(s)
    * Interaction Preference (Implied, useful context)
    * Bio (potentially truncated)
    (User Story F2.1 AC 1, referencing `users` schema fields)
* Include interactive elements (buttons or gestures) for "Like" (or Connect/Request) and "Pass" (or Skip) actions (User Story F2.1 AC 2, F2.2).
* Adhere to visual design from UI PDF Page 10 (Reference), likely showing a stack of cards or a single prominent card.
* Use Brand Guidelines for card styling, typography, colors, and button/icon styling.
* Include handling for an "empty state" when there are no more potential matches to show (User Story F2.1 AC 3).

**Action:**
1.  Create the UI component for the Matching Screen.
2.  Implement a card component to display user profile information as specified.
3.  Integrate a card stack or swiper library/component to manage the display and interaction of cards.
4.  Add "Like" and "Pass" buttons/icons to the UI, associated with the card actions.
5.  Design and implement the empty state view (e.g., a message like "No more profiles right now. Check back later!").

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the screen display profiles in a card format (F2.1 AC 1)? Does each card show the required user info (F2.1 AC 1)? Are Like/Pass controls present (F2.1 AC 2)? Is an empty state handled (F2.1 AC 3)?
2.  **Review Test Cases:** Does the UI layout support TC_F2.1_01 (displaying card with info and action buttons)?
3.  **Validate UI:** Does the UI match the Mockup (Page 10)? Does it adhere to Brand Guidelines (Card Styling, Typography, Buttons/Icons)? Is the empty state visually clear?
4.  **Functionality Check:** Does the screen structure support displaying cards one by one? Are the action buttons/areas clearly identifiable? Does the empty state display when appropriate (initially, before data loading)?
5.  **List Assumptions/Issues:** List assumptions about the specific card swiper library used, truncation logic for bio, exact icons/text for Like/Pass, and empty state design details.
"
---
**Task #16:** Implement Matching Logic (Fetching Potential Matches - Basic)
**Status:** To Do
**Relevant Artifacts:** User Story F2.1, Database Schema (`users` collection), PRD Sec 8 (Algorithm Question - MVP approach), Test Cases (TC_F2.1_02, TC_F2.1_03)
**AI Coding Prompt:**
"
**Objective:** Implement the backend/client logic to fetch a list of potential matches based on MVP criteria and display them on the Matching screen.

**Context & Requirements:**
* When the Matching screen loads or needs more profiles:
    * Fetch a batch of user profiles from the `users` collection that meet the MVP matching criteria.
    * **MVP Criteria (Addressing PRD Sec 8):**
        * Exclude the current user.
        * Exclude users already swiped on (liked/passed) by the current user (Requires tracking swipes - see Task #17).
        * Exclude users who have already passed on the current user (Requires tracking swipes - see Task #17).
        * Match based on `interactionPreference` (e.g., if current user wants 'Mock Interview', find users wanting 'Mock Interview' or 'Both').
        * Match based on roles (e.g., current user's `targetRoles` includes potential match's `currentRole`, OR vice-versa).
        * Consider `accountVisibility` != 'hidden'.
        * Basic location proximity might be considered Post-MVP unless specified otherwise.
    * Populate the card stack (Task #15) with the fetched profiles.
    * Handle the case where no matching profiles are found (trigger the empty state UI) (User Story F2.1 AC 3).
    * Implement pagination or batch loading to manage performance.

**Action:**
1.  Determine where swipe history will be stored (e.g., subcollections under the user: `users/{userId}/likes`, `users/{userId}/passes`). Update Schema if needed.
2.  Implement the database query logic (potentially in a backend function called by the client, or directly on the client if rules allow) to fetch users based on the MVP criteria (excluding self, excluding already swiped, matching preference, matching roles, visible).
3.  Integrate this fetching logic into the Matching screen component.
4.  Manage the state of fetched profiles and feed them to the card stack UI.
5.  Trigger the empty state UI when the fetch returns no results or the local queue is empty.
6.  Implement logic to fetch the next batch when the current batch runs low.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the logic attempt to fetch profiles based on some criteria (F2.1 AC 1)? Does it handle the empty state (F2.1 AC 3)?
2.  **Review Test Cases:** Does the fetching logic correctly retrieve potential matches based on MVP criteria (simulated in TC_F2.1_02)? Does it correctly display the empty state when no matches are found (TC_F2.1_03)? Does it exclude users already swiped on (needs Task #17 context)?
3.  **Validate UI:** Does the card stack populate with fetched user data? Does the empty state appear correctly when no matches are returned?
4.  **Functionality Check:** Describe the query logic: How does it filter users based on preferences, roles, visibility, and swipes (even if swipe tracking isn't fully built yet)? How is pagination handled?
5.  **List Assumptions/Issues:** List assumptions about the exact MVP matching algorithm details (role matching logic, preference matching), swipe tracking mechanism location (confirm schema update if needed), pagination strategy, and where the query logic resides (client/backend).
"
---
**Task #17:** Implement Swipe Actions (Like/Pass) & Match Creation
**Status:** To Do
**Relevant Artifacts:** User Story F2.2, F2.3, Database Schema (`users`, `matches` collection, potentially swipe tracking subcollections), Test Cases (TC_F2.2_01, TC_F2.2_02, TC_F2.3_01, TC_F2.3_02)
**AI Coding Prompt:**
"
**Objective:** Implement the logic for handling user swipe actions (Like/Pass) on the Matching screen and creating a match record when mutual likes occur.

**Context & Requirements:**
* When the user performs a "Pass" action (button or gesture) on a profile card (User Story F2.2):
    * Record this action to prevent showing the same profile again (e.g., add passed `userId` to `users/{currentUser}/passes` subcollection or array) (User Story F2.2 AC 1).
    * Remove the card from the view and potentially load the next one (User Story F2.2 AC 2).
* When the user performs a "Like" action (button or gesture) on a profile card (User Story F2.3):
    * Record this action (e.g., add liked `userId` to `users/{currentUser}/likes` subcollection or array) (User Story F2.3 AC 1).
    * Check if the liked user has already liked the current user (check `users/{likedUserId}/likes` for `currentUserId`).
    * **If mutual like (Match):**
        * Create a new document in the `matches` collection (User Story F2.3 AC 2).
        * The `matches` document should include: `matchId` (unique ID), `participantIds` (array with both user IDs), `participantInfo` (map with denormalized basic info like name/photoUrl for both users), `createdAt` timestamp, `status` ('active'), `lastMessagePreview` (null), `lastMessageTimestamp` (null), `unreadCounts` (map with userId: 0 for both). See Database Schema for details.
        * Trigger a notification for both users about the new match (User Story F5.1 - backend logic in Task #22).
        * Provide immediate UI feedback (e.g., "It's a Match!" animation/popup) (User Story F2.3 AC 2).
    * **If not a mutual like:** No immediate match feedback is needed beyond recording the like.
    * Remove the card from the view and potentially load the next one (User Story F2.3 AC 1).

**Action:**
1.  Finalize and implement the swipe tracking mechanism in the database (e.g., `users/{userId}/likes/{likedUserId}` and `users/{userId}/passes/{passedUserId}` documents).
2.  Connect the UI actions (Like/Pass buttons/gestures from Task #15) to trigger the corresponding logic.
3.  Implement the "Pass" logic: Record pass in DB, remove card.
4.  Implement the "Like" logic: Record like in DB, check for mutual like, create `matches` document if mutual, trigger notification (placeholder call), show match feedback UI, remove card.
5.  Ensure the fetching logic (Task #16) correctly uses the swipe tracking data to filter profiles.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does Pass record the action and dismiss card (F2.2 AC 1, 2)? Does Like record the action (F2.3 AC 1)? Does mutual Like create a `matches` doc and show feedback (F2.3 AC 2)?
2.  **Review Test Cases:** Does the logic cover TC_F2.2_01 (record pass), TC_F2.2_02 (dismiss card on pass)? Does it cover TC_F2.3_01 (record like, check mutual)? Does it cover TC_F2.3_02 (create match doc, show feedback)?
3.  **Validate UI:** Is the "It's a Match!" feedback displayed correctly on a mutual like? Do cards dismiss smoothly after a swipe?
4.  **Functionality Check:** Walk through Pass: Swipe Pass -> DB write (pass recorded) -> Card dismissed. Walk through Like (No Match): Swipe Like -> DB write (like recorded) -> Card dismissed. Walk through Like (Match): User A likes B -> User B likes A -> DB write (A likes B), DB write (B likes A), Check mutual -> DB write (`matches` doc created) -> Match UI Feedback -> Card dismissed. Verify `matches` doc structure and denormalized data.
5.  **List Assumptions/Issues:** Confirm swipe tracking schema. List assumptions about match feedback UI details, notification trigger mechanism (placeholder ok), and error handling for DB writes.
"
---
**Task #18:** Implement Connections/Chat List Screen UI
**Status:** To Do
**Relevant Artifacts:** User Story F3.1, PRD Page 11 (Mockup Ref), Database Schema (`matches` collection - denormalized info), Brand Guidelines (Sec 3: Colors, Sec 4: Typography, Sec 5: UI Elements), Test Cases (TC_F3.1_01)
**AI Coding Prompt:**
"
**Objective:** Implement the user interface for the Connections/Chat List screen, displaying the user's active matches.

**Context & Requirements:**
* This screen is a primary tab in the main navigation (Task #11).
* Display a list of the user's active matches (connections) (User Story F3.1 AC 1).
* Each list item should represent one match and display:
    * The other user's profile picture.
    * The other user's full name.
    * A preview of the last message sent in the chat (if any).
    * The timestamp of the last message (if any).
    * An indicator for unread messages (if any).
    (User Story F3.1 AC 1, using denormalized data from `matches` document: `participantInfo`, `lastMessagePreview`, `lastMessageTimestamp`, `unreadCounts`).
* The list should be ordered, typically by the timestamp of the last message (most recent first).
* Tapping on a list item should navigate the user to the specific chat screen for that match (User Story F3.1 AC 2, F3.4).
* Adhere to visual design from UI PDF Page 11 (Reference).
* Use Brand Guidelines for list item layout, typography, colors, spacing, and unread indicators.
* Include handling for an empty state if the user has no active matches (User Story F3.1 AC 3).

**Action:**
1.  Create the UI component for the Connections/Chat List Screen.
2.  Implement a list component (e.g., FlatList, ScrollView).
3.  Create a reusable list item component to display the match information (picture, name, preview, timestamp, unread indicator).
4.  Implement the empty state view (e.g., "No connections yet. Start matching!").
5.  Make each list item tappable, preparing for navigation logic.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the screen structure support displaying a list of matches (F3.1 AC 1)? Does the list item design include placeholders for the required info (F3.1 AC 1)? Is an empty state handled (F3.1 AC 3)? Are list items tappable (F3.1 AC 2)?
2.  **Review Test Cases:** Does the UI layout support TC_F3.1_01 (displaying list items with photo, name, preview, timestamp, unread status)?
3.  **Validate UI:** Does the UI match the Mockup (Page 11)? Does it adhere to Brand Guidelines (List Item Styling, Typography, Unread Indicator)? Is the empty state visually clear?
4.  **Functionality Check:** Does the screen structure allow for a vertical list? Does the list item component have distinct areas for each piece of information? Does the empty state display appropriately (initially)?
5.  **List Assumptions/Issues:** List assumptions about the specific layout of list items, unread indicator style, timestamp formatting, and empty state design details.
"
---
**Task #19:** Implement Chat List Logic (Fetching Matches/Chats)
**Status:** To Do
**Relevant Artifacts:** User Story F3.1, Database Schema (`matches` collection, `users` collection for current user ID), Test Cases (TC_F3.1_02, TC_F3.1_03)
**AI Coding Prompt:**
"
**Objective:** Implement the logic to fetch the user's active matches and populate the Connections/Chat List screen.

**Context & Requirements:**
* When the Connections/Chat List screen loads:
    * Fetch all documents from the `matches` collection where the `participantIds` array contains the current user's ID and the `status` is 'active'.
    * Set up a real-time listener (e.g., Firestore `onSnapshot`) to automatically update the list when changes occur (new match, new message updates preview/timestamp, status changes).
    * Order the fetched matches based on `lastMessageTimestamp` (descending, most recent first). Matches with no messages might appear at the bottom or ordered by `createdAt`.
    * Use the denormalized data within each `matches` document (`participantInfo`, `lastMessagePreview`, `lastMessageTimestamp`, `unreadCounts`) to populate the UI list (Task #18). Extract the *other* participant's info to display.
    * Handle the empty state: If the query returns no active matches, display the empty state UI (User Story F3.1 AC 3).
    * Implement navigation: When a list item is tapped, navigate to the Chat Screen (Task #20), passing necessary identifiers (e.g., `matchId`, other user's ID, other user's name/photo).

**Action:**
1.  Implement the database query logic with a real-time listener to fetch active matches for the current user, ordered by `lastMessageTimestamp`.
2.  Integrate this fetching logic into the Connections/Chat List component.
3.  Manage the state of the fetched matches list.
4.  Map the fetched data to the UI list items, ensuring the correct participant's info and message details are displayed.
5.  Trigger the empty state UI based on the query results.
6.  Implement the navigation logic triggered by tapping a list item, passing required parameters to the Chat Screen route.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the logic fetch active matches for the user (F3.1 AC 1)? Does it use real-time updates? Is the list ordered correctly? Does tapping navigate to the chat screen (F3.1 AC 2)? Is the empty state handled (F3.1 AC 3)?
2.  **Review Test Cases:** Does the logic correctly fetch and display matches based on `participantIds` and `status` (TC_F3.1_02)? Is the list ordered by `lastMessageTimestamp`? Does it handle the empty state correctly (TC_F3.1_03)? Does tapping navigate?
3.  **Validate UI:** Does the list populate with data from the database? Does the order update correctly when new messages arrive (requires Task #21)? Does the empty state show/hide correctly?
4.  **Functionality Check:** Describe the query: How does it filter by `participantIds` and `status`? How is ordering applied? How does the real-time listener work? What data is passed during navigation?
5.  **List Assumptions/Issues:** List assumptions about the exact ordering for items with null timestamps, error handling for the listener, and the specific parameters needed by the Chat Screen.
"
---
**Task #20:** Implement Chat Screen UI
**Status:** To Do
**Relevant Artifacts:** User Story F3.4, PRD Page 12 (Mockup Ref), Brand Guidelines (Sec 3: Colors, Sec 4: Typography, Sec 5: UI Elements), Test Cases (TC_F3.4_01)
**AI Coding Prompt:**
"
**Objective:** Implement the user interface for the individual Chat screen where users exchange messages.

**Context & Requirements:**
* This screen is navigated to from the Connections/Chat List screen (Task #19).
* Display a header showing the other participant's name and potentially their profile picture. Include a back button to return to the chat list.
* Display the chat messages in a chronological sequence (oldest at the top, newest at the bottom) (User Story F3.4 AC 1).
* Differentiate visually between messages sent by the current user and messages received from the other participant (e.g., alignment, background color) (User Story F3.4 AC 1).
* Include a text input field at the bottom for composing new messages (User Story F3.4 AC 2).
* Include a "Send" button next to the text input field, enabled only when the input field is not empty (User Story F3.4 AC 2).
* Adhere to visual design from UI PDF Page 12 (Reference).
* Use Brand Guidelines for message bubble styling, colors, typography, input field styling, and button styling.

**Action:**
1.  Create the UI component for the Chat Screen.
2.  Implement the header with the other user's info (passed via navigation) and a back button.
3.  Implement a scrollable view (e.g., FlatList, inverted for chat) to display message bubbles.
4.  Create message bubble components for sent and received messages, styling them differently according to Brand Guidelines.
5.  Implement the message input area at the bottom, including the text input and the Send button.
6.  Ensure the Send button is initially disabled.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the UI structure support displaying messages chronologically (F3.4 AC 1)? Are sent/received messages visually distinct (F3.4 AC 1)? Is there a text input and Send button (F3.4 AC 2)?
2.  **Review Test Cases:** Does the UI layout support TC_F3.4_01 (displaying header, message list area, input field, send button)?
3.  **Validate UI:** Does the UI match the Mockup (Page 12)? Does it adhere to Brand Guidelines (Header, Message Bubbles, Input Area, Colors, Typography)? Is the Send button initially disabled?
4.  **Functionality Check:** Does the screen structure allow for scrolling through messages? Are the input field and Send button positioned correctly? Does the header display the correct participant's info?
5.  **List Assumptions/Issues:** List assumptions about message timestamp display format within bubbles, handling of very long messages, and specific styling details if mockup is unclear.
"
---
**Task #21:** Implement Chat Logic (Sending/Receiving Messages)
**Status:** To Do
**Relevant Artifacts:** User Story F3.4, F3.5, Database Schema (`matches/{matchId}/messages` subcollection), Test Cases (TC_F3.4_02, TC_F3.4_03, TC_F3.5_01)
**AI Coding Prompt:**
"
**Objective:** Implement the logic for sending new messages and receiving/displaying messages in real-time on the Chat screen.

**Context & Requirements:**
* **Receiving Messages:**
    * When the Chat screen loads for a specific `matchId`:
    * Fetch messages from the `matches/{matchId}/messages` subcollection, ordered by `timestamp` (ascending).
    * Set up a real-time listener (e.g., Firestore `onSnapshot`) on this subcollection to receive new messages instantly (User Story F3.5 AC 1).
    * Display the fetched/received messages in the chat view (Task #20), distinguishing between sent and received.
* **Sending Messages:**
    * Enable the "Send" button only when the text input is not empty (User Story F3.4 AC 2).
    * When the "Send" button is tapped:
        * Create a new message object containing: `messageId` (unique ID), `senderId` (current user's ID), `text` (from input field), `timestamp` (server timestamp).
        * Add this message object as a new document to the `matches/{matchId}/messages` subcollection (User Story F3.4 AC 3).
        * Clear the text input field after successful sending (User Story F3.4 AC 3).
        * **Update Match Document (Denormalization):** Update the parent `matches/{matchId}` document with `lastMessagePreview` (the new message text), `lastMessageTimestamp` (the new timestamp), and increment the `unreadCounts` for the *other* participant. This is crucial for the Chat List screen (Task #19). This update might be done via a Cloud Function triggered by the new message write.
        * Trigger a push notification to the receiving user (User Story F5.2 - backend logic in Task #22).
* Handle potential errors during message sending or fetching.

**Action:**
1.  Implement the database query with a real-time listener to fetch messages for the current `matchId`, ordered by `timestamp`.
2.  Integrate fetching logic into the Chat screen component, managing the message list state and updating the UI.
3.  Implement the "Send" button logic:
    * Enable/disable based on input content.
    * On tap: Create message object, write to `messages` subcollection.
    * Clear input field.
    * Trigger update of the parent `matches` document (either directly or assume a Cloud Function handles it).
    * Trigger notification (placeholder call).
4.  Handle errors for DB operations.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Are messages fetched and displayed (F3.4 AC 1)? Is the Send button enabled correctly (F3.4 AC 2)? Does Send write the message to the DB and clear the input (F3.4 AC 3)? Are new messages received in real-time (F3.5 AC 1)? Is the parent `matches` doc updated (denormalization)?
2.  **Review Test Cases:** Does the logic fetch and display messages (TC_F3.4_01 setup)? Does Send button enable/disable correctly (TC_F3.4_02)? Does sending a message add it to the DB, clear input, and update the UI (TC_F3.4_03)? Does the real-time listener receive and display new messages (TC_F3.5_01)?
3.  **Validate UI:** Do sent messages appear immediately? Do received messages appear in real-time? Does the Send button behave as expected?
4.  **Functionality Check:** Walk through sending: Type message -> Send enabled -> Tap Send -> DB write (message) -> Input cleared -> UI updates -> DB update (match doc - check fields) -> Notification triggered. Walk through receiving: Another user sends message -> Listener fires -> UI updates with new message.
5.  **List Assumptions/Issues:** Confirm where the `matches` document update logic resides (client vs. Cloud Function - assume Function for robustness). List assumptions about error handling details and notification trigger mechanism.
"
---
**Task #22:** Implement Notification System (Backend Logic for Match/Message)
**Status:** To Do
**Relevant Artifacts:** User Story F5.1, F5.2, Database Schema (`users`, `matches`, `messages`, `notifications` subcollection or similar), Push Notification Service (e.g., FCM)
**AI Coding Prompt:**
"
**Objective:** Implement the backend logic (e.g., using Cloud Functions) to create notification records and trigger push notifications upon new matches and new messages.

**Context & Requirements:**
* **New Match Notification (User Story F5.1):**
    * Trigger: A new document is created in the `matches` collection (Task #17).
    * Action:
        * For *each* participant in the match:
            * Create a notification record (e.g., in `users/{userId}/notifications` subcollection) containing: `notificationId`, `type`='new_match', `senderId` (the *other* participant's ID), `senderName` (optional, denormalized), `senderPhotoUrl` (optional, denormalized), `matchId`, `timestamp`, `isRead`=false.
            * Retrieve the recipient's push notification token(s) from their `users` document (`pushTokens` field - needs adding to schema).
            * If token(s) exist, send a push notification payload (via FCM or similar) to the recipient's device(s) indicating a new match. Payload should include necessary data to handle the notification on the client (e.g., `type`, `matchId`, `senderName`).
* **New Message Notification (User Story F5.2):**
    * Trigger: A new document is created in a `matches/{matchId}/messages` subcollection (Task #21).
    * Action:
        * Determine the recipient (the user who is *not* the `senderId` of the message).
        * Create a notification record for the recipient (e.g., in `users/{recipientId}/notifications`) containing: `notificationId`, `type`='new_message', `senderId`, `senderName`, `senderPhotoUrl`, `matchId`, `messagePreview` (text snippet), `timestamp`, `isRead`=false.
        * Retrieve the recipient's push notification token(s) from their `users` document.
        * If token(s) exist, send a push notification payload to the recipient's device(s) indicating a new message. Payload should include necessary data (e.g., `type`, `matchId`, `senderName`, `messagePreview`).
* **Schema Update:** Add a `pushTokens` field (likely an array of strings) to the `users` collection schema to store device tokens.

**Action:**
1.  Update the `users` collection schema to include a `pushTokens` field.
2.  Implement a Cloud Function triggered by the creation of documents in the `matches` collection. This function performs the actions described for New Match Notifications.
3.  Implement a Cloud Function triggered by the creation of documents in `matches/{matchId}/messages`. This function performs the actions described for New Message Notifications.
4.  Integrate with the chosen push notification service (e.g., Firebase Cloud Messaging) to send the push notifications.
5.  Define the structure for the `notifications` subcollection under `users`.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does a new match trigger notification record creation and push attempt for both users (F5.1)? Does a new message trigger notification record creation and push attempt for the recipient (F5.2)?
2.  **Review Test Cases:** N/A directly (backend logic), but enables TC_F5.1_01 and TC_F5.2_01 preconditions.
3.  **Validate UI:** N/A (backend logic).
4.  **Functionality Check:** Describe the trigger and actions for the New Match function. Describe the trigger and actions for the New Message function. How are push tokens retrieved? What data is included in the notification record and push payload for each type? Is the `notifications` subcollection structure defined? Is the `pushTokens` field added to `users` schema?
5.  **List Assumptions/Issues:** List assumptions about the specific Cloud Function triggers, push notification service APIs, error handling within functions (e.g., user has no token), and the exact structure of the `notifications` subcollection.
"
---
**Task #23:** Implement Push Notifications (Client Setup & Handling)
**Status:** To Do
**Relevant Artifacts:** User Story F5.1, F5.2, Test Cases (TC_F5.1_01, TC_F5.2_01), Push Notification Service Client SDK (e.g., react-native-firebase)
**AI Coding Prompt:**
"
**Objective:** Configure the client application to receive push notifications and handle user interactions with them.

**Context & Requirements:**
* **Setup & Token Management:**
    * Integrate the necessary client-side SDK for the push notification service (e.g., FCM).
    * Request permission from the user to receive push notifications (typically on app start or after login).
    * On obtaining permission, retrieve the device's unique push notification token.
    * Save this token to the current user's document in the `users` collection (`pushTokens` array field - see Task #22). Handle adding/removing tokens if the user logs in on multiple devices or the token refreshes.
* **Receiving Notifications:**
    * Implement listeners to handle incoming push notifications when the app is in the foreground, background, or terminated.
    * **Foreground:** Decide how to alert the user (e.g., subtle in-app banner, update badge count).
    * **Background/Terminated:** The notification should appear in the device's system tray/notification center.
* **Handling Notification Taps:**
    * When a user taps on a push notification:
        * If it's a 'new_match' notification (F5.1), navigate the user to the relevant Chat Screen (Task #20) or potentially the matched user's profile. Use data from the notification payload (e.g., `matchId`).
        * If it's a 'new_message' notification (F5.2), navigate the user directly to the corresponding Chat Screen (Task #20). Use data from the payload (e.g., `matchId`).
* Update application badge count based on unread notifications if applicable.

**Action:**
1.  Add push notification libraries/SDKs to the client project.
2.  Implement permission requests for notifications.
3.  Implement logic to get the device token and save/update it in the user's Firestore document (`users/{userId}/pushTokens`).
4.  Implement background message handler to display notifications when the app is not in the foreground.
5.  Implement foreground message handler to provide in-app feedback.
6.  Implement logic to handle notification taps, extracting data from the payload and navigating to the appropriate screen (Chat or Profile).
7.  (Optional) Implement badge count updates.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the app request permission? Is the token saved to Firestore? Are notifications received (foreground/background)? Does tapping a match notification navigate correctly (F5.1)? Does tapping a message notification navigate correctly (F5.2)?
2.  **Review Test Cases:** Does the implementation allow receiving a match notification (TC_F5.1_01)? Does it allow receiving a message notification (TC_F5.2_01)? Does tapping them lead to the correct screen?
3.  **Validate UI:** Do notifications appear in the system tray? Is foreground notification handling implemented? Does tapping the notification perform the correct navigation?
4.  **Functionality Check:** Describe the token registration process. Describe how foreground and background notifications are handled. Describe the logic for extracting data from the payload and navigating upon notification tap for both match and message types.
5.  **List Assumptions/Issues:** List assumptions about specific library APIs, foreground notification UI, badge count logic, and exact data expected in the push payload from the backend (Task #22).
"
---
**Task #24:** Implement Notification Center UI & Logic
**Status:** To Do
**Relevant Artifacts:** User Story F5.7, PRD Page 13 (Mockup Ref), Database Schema (`users/{userId}/notifications` subcollection), Brand Guidelines, Test Cases (TC_F5.7_01 to TC_F5.7_09)
**AI Coding Prompt:**
"
**Objective:** Implement the Notification Center screen, displaying a history of notifications and handling read status.

**Context & Requirements:**
* **UI & Access:**
    * Provide access to the Notification Center via the main navigation (Task #11).
    * Display a list of notifications fetched from the user's `notifications` subcollection (created in Task #22) (User Story F5.7 AC 1).
    * Order notifications chronologically, newest first (User Story F5.7 AC 2).
    * Each list item should display information based on the notification `type`:
        * **'new_match':** Show sender's name/picture, text like "You have a new match!", timestamp (F5.7 AC 3).
        * **'new_message':** Show sender's name/picture, message preview, timestamp (F5.7 AC 4).
    * Visually differentiate unread notifications (e.g., background color, dot) (F5.7 AC 7).
    * Handle empty state if no notifications exist (TC_F5.7_09).
    * Adhere to UI PDF Page 13 (Reference) and Brand Guidelines.
* **Logic:**
    * Fetch notifications from `users/{userId}/notifications`, ordered by `timestamp` descending. Use a real-time listener for updates.
    * Tapping a 'new_match' notification navigates to the Chat screen or matched user's profile (F5.7 AC 5).
    * Tapping a 'new_message' notification navigates to the corresponding Chat screen (F5.7 AC 6).
    * Implement read status management: Mark a notification as read (`isRead`=true in Firestore) when the user taps on it, or potentially when the Notification Center is opened (clarify requirement - assume tap for now) (F5.7 AC 8). Update the UI accordingly.

**Action:**
1.  Create the UI component for the Notification Center screen.
2.  Implement a list view to display notifications.
3.  Create list item components tailored for 'new_match' and 'new_message' types, including read/unread styling.
4.  Implement the database query with a real-time listener to fetch notifications, ordered by timestamp.
5.  Integrate fetching logic, manage state, and populate the UI list.
6.  Implement navigation logic for tapping notifications (reuse logic from push notification handling if possible).
7.  Implement the logic to update the `isRead` status in Firestore when a notification is interacted with (e.g., tapped).
8.  Implement the empty state view.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Is the list displayed chronologically (F5.7 AC 1, 2)? Are match/message notifications displayed correctly (F5.7 AC 3, 4)? Does tapping navigate correctly (F5.7 AC 5, 6)? Is read/unread status shown and updated (F5.7 AC 7, 8)? Is empty state handled?
2.  **Review Test Cases:** Does the UI support TC_F5.7_01 (access)? Does it fetch/display correctly (TC_F5.7_02)? Does it differentiate types (TC_F5.7_03, TC_F5.7_04)? Does tapping navigate (TC_F5.7_05, TC_F5.7_06)? Is read/unread shown (TC_F5.7_07) and updated (TC_F5.7_08)? Is empty state handled (TC_F5.7_09)?
3.  **Validate UI:** Does the UI match the Mockup (Page 13)? Does it adhere to Brand Guidelines? Do read/unread indicators work? Does the empty state appear correctly?
4.  **Functionality Check:** Describe fetching/ordering logic. Describe navigation on tap. Describe how `isRead` status is updated in Firestore and reflected in the UI.
5.  **List Assumptions/Issues:** Clarify when notifications are marked read (on tap vs. on open). List assumptions about specific UI styling and empty state text.
"
---
**Task #25:** Implement Logout Functionality
**Status:** To Do
**Relevant Artifacts:** User Story F1.10, Test Cases (TC_F1.10_01), Authentication Service SDK
**AI Coding Prompt:**
"
**Objective:** Implement the ability for users to log out of the application.

**Context & Requirements:**
* Provide a "Logout" button or menu item, typically accessible from the Profile screen (Task #12) or Account Settings.
* When the user confirms they want to log out:
    * Call the authentication service's sign-out method (e.g., Firebase Auth `signOut()`) (User Story F1.10 AC 1).
    * Clear any locally stored user session data or state.
    * Navigate the user back to the initial Landing or Login screen (User Story F1.10 AC 1).
    * Consider removing the device's push notification token from the user's `pushTokens` array in Firestore upon logout to prevent sending notifications to a logged-out device.

**Action:**
1.  Connect the "Logout" button/option UI element (from Task #12) to the logout logic.
2.  Implement the logout function:
    * (Optional but recommended) Remove the current device's push token from the `users/{userId}/pushTokens` array in Firestore.
    * Call the auth service `signOut()` method.
    * Clear local user state (e.g., Redux store, context).
    * Navigate to the Landing/Login screen using the navigation service, potentially resetting the navigation stack.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does tapping Logout sign the user out via the auth service and navigate them to the Login/Landing screen (F1.10 AC 1)?
2.  **Review Test Cases:** Does the implementation correctly perform sign-out and navigation as described in TC_F1.10_01?
3.  **Validate UI:** Does the user land on the Login or Landing screen after logging out?
4.  **Functionality Check:** Walk through: Tap Logout -> (Optional: DB update pushTokens) -> Auth sign out call -> Clear local state -> Navigation to Login/Landing. Attempting to access protected screens after logout should fail or redirect to login.
5.  **List Assumptions/Issues:** Confirm whether push token removal on logout is required. List assumptions about local state management clearing and navigation stack resetting.
"
---
**Task #26:** Implement Account Settings (Visibility - Basic)
**Status:** To Do
**Relevant Artifacts:** User Story F1.11, Database Schema (`users.accountVisibility`), Test Cases (TC_F1.11_01), PRD Sec 8 (Visibility Question)
**AI Coding Prompt:**
"
**Objective:** Implement a basic Account Settings screen allowing users to control their profile visibility.

**Context & Requirements:**
* Provide access to an "Account Settings" screen, likely from the Profile screen (Task #12).
* On the Account Settings screen, include an option to control profile visibility (User Story F1.11 AC 1).
* **MVP Visibility Option (Addressing PRD Sec 8):** Provide a simple toggle or selection for "Visible" / "Hidden".
    * **Visible:** Profile can appear in matching results for others.
    * **Hidden:** Profile is temporarily excluded from appearing in matching results for others. User can still use the app, see their matches, chat, etc.
* Display the user's current visibility setting.
* When the user changes the setting:
    * Update the `accountVisibility` field in their `users` document in Firestore (User Story F1.11 AC 2).
    * Provide feedback that the setting was saved.
* Ensure the matching logic (Task #16) respects the `accountVisibility` field.

**Action:**
1.  Create the UI component for the Account Settings screen.
2.  Add a control (e.g., Switch, Segmented Control) for the "Profile Visibility" setting, reflecting the current value from the user's data.
3.  Implement the logic to update the `users.accountVisibility` field in Firestore when the user changes the setting.
4.  Provide user feedback on save (e.g., toast message).
5.  Ensure navigation to/from this screen is set up (from Profile screen).

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Does the settings screen offer a visibility control (F1.11 AC 1)? Does changing the setting update the `accountVisibility` field in Firestore (F1.11 AC 2)?
2.  **Review Test Cases:** Does the UI allow viewing and changing the visibility setting (TC_F1.11_01)? Does the change persist in the database?
3.  **Validate UI:** Is the current setting displayed correctly? Does the control allow changing the setting? Is feedback provided on save? Does the screen adhere to Brand Guidelines?
4.  **Functionality Check:** Walk through: View setting -> Change setting -> DB update (`accountVisibility` field) -> Save feedback. Verify the matching logic (Task #16) correctly filters based on this field.
5.  **List Assumptions/Issues:** Confirm the MVP options are 'Visible'/'Hidden'. List assumptions about the specific UI control used and feedback mechanism.
"
---
**Task #27:** Implement Premium Feature Gates (UI)
**Status:** To Do
**Relevant Artifacts:** User Story F6.2, PRD Sec 2.3 (Premium Features), PRD Sec 5.2 (Post-MVP), Brand Guidelines (Sec 5: UI Elements), Database Schema (`users.isPremium`), Test Cases (TC_F6.2_xx - Placeholder)
**AI Coding Prompt:**
"
**Objective:** Implement the UI elements that visually distinguish premium features and prompt non-premium users to subscribe.

**Context & Requirements:**
* Identify features designated as premium (e.g., Advanced Matching Filters, Read Receipts, Profile Boost - PRD Sec 2.3).
* For non-premium users (`users.isPremium` is false):
    * Clearly indicate premium features in the UI (e.g., using a lock icon, 'Premium' badge, dimmed appearance) (User Story F6.2 AC 1).
    * When a non-premium user attempts to access or activate a premium feature:
        * Prevent the feature's core functionality from executing.
        * Display a modal, screen, or prompt explaining the feature is premium (User Story F6.2 AC 2).
        * Include a clear call-to-action (CTA) button within the prompt to navigate the user to the Subscription Purchase screen/flow (Task #28) (User Story F6.2 AC 3).
* For premium users (`users.isPremium` is true):
    * Premium features should appear unlocked and be fully functional.
* Use Brand Guidelines for styling premium indicators and subscription prompts.

**Action:**
1.  Refactor or wrap UI components associated with premium features to check the user's `isPremium` status.
2.  Implement the visual indicators (icons, badges, styling) for locked features for non-premium users.
3.  Create a reusable modal or screen component for the premium subscription prompt, including descriptive text and the CTA button.
4.  Implement the logic to display this prompt and block feature access when a non-premium user interacts with a gated feature.
5.  Connect the CTA button in the prompt to navigate to the Subscription Purchase screen (placeholder initially, link to Task #28).

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Are premium features visually indicated as locked for free users (F6.2 AC 1)? Does interacting with a locked feature show a subscription prompt (F6.2 AC 2)? Does the prompt have a CTA linking to the subscription flow (F6.2 AC 3)? Are features unlocked for premium users?
2.  **Review Test Cases:** Does the UI correctly gate features based on `isPremium` status (TC_F6.2_01 - Placeholder)? Does the subscription prompt appear correctly (TC_F6.2_02 - Placeholder)? Does the CTA navigate correctly (TC_F6.2_03 - Placeholder)?
3.  **Validate UI:** Do the premium indicators match Brand Guidelines? Is the subscription prompt clear and visually appealing? Does the CTA button stand out?
4.  **Functionality Check:** Walk through as free user: Attempt to use premium feature -> Prompt appears -> Tap CTA -> Navigation occurs. Walk through as premium user: Attempt to use premium feature -> Feature works -> No prompt appears. Check multiple premium features.
5.  **List Assumptions/Issues:** List the specific features identified as premium for gating. List assumptions about the prompt's design and the exact navigation target for the subscription flow.
"
---
**Task #28:** Implement Subscription Purchase Flow (Apple/Google Pay)
**Status:** To Do
**Relevant Artifacts:** User Story F6.1, PRD Sec 2.3, PRD Sec 5.2, Database Schema (`users.isPremium`, `subscriptions` collection), Platform Billing Libraries (StoreKit/Google Play Billing), Test Cases (TC_F6.1_xx - Placeholder)
**AI Coding Prompt:**
"
**Objective:** Implement the in-app purchase flow allowing users to subscribe to Mockaccino Premium using native platform billing (Apple App Store / Google Play Store).

**Context & Requirements:**
* **Subscription Screen UI:**
    * Create a dedicated screen (or modal) accessible via premium feature gates (Task #27) or potentially a 'Go Premium' option in settings/profile.
    * Clearly display the benefits of subscribing (list premium features).
    * Show subscription options (e.g., monthly/annual pricing - define product IDs).
    * Include a prominent "Subscribe" or "Start Free Trial" (if applicable) button.
    * Include links to restore purchases and potentially terms/privacy policy related to subscriptions.
* **Purchase Logic:**
    * Integrate the appropriate platform-specific in-app purchase library (e.g., `react-native-iap`, StoreKit, Google Play Billing).
    * Configure subscription product IDs matching those set up in App Store Connect / Google Play Console.
    * When the user taps "Subscribe":
        * Initiate the purchase flow using the library, requesting payment via the user's Apple/Google account (User Story F6.1 AC 1).
    * Handle purchase callbacks/listeners:
        * **Success:**
            * Verify the purchase receipt with your backend or directly on the device (backend recommended for security).
            * On successful verification, update the user's status in Firestore: set `users.isPremium = true` (User Story F6.1 AC 2).
            * Optionally, create a record in the `subscriptions` collection tracking the `userId`, `productId`, `purchaseDate`, `expiryDate`, `status` ('active'), `originalTransactionId`, etc. (See DB Schema).
            * Unlock premium features in the UI immediately. Provide success feedback.
        * **Failure/Cancellation:** Handle errors (e.g., payment declined, user cancelled) gracefully. Provide appropriate user feedback (User Story F6.1 AC 3). Stay on the subscription screen.
* **Restore Purchases:**
    * Implement a "Restore Purchases" button/mechanism that uses the billing library to check the user's platform account for existing active subscriptions and re-apply premium status if found (User Story F6.1 AC 4).

**Action:**
1.  Add and configure the in-app purchase library for both iOS and Android.
2.  Define subscription product IDs in the code and set them up in App Store Connect / Google Play Console.
3.  Create the Subscription screen UI, displaying benefits, pricing, CTA, and restore/legal links.
4.  Implement the purchase initiation logic when the Subscribe button is tapped.
5.  Implement purchase listeners/callbacks to handle success, failure, and cancellation.
6.  Implement receipt validation logic (ideally via a secure backend endpoint).
7.  Implement the database updates (`users.isPremium`, `subscriptions` record) upon successful, validated purchase.
8.  Implement the UI update logic to unlock features upon successful subscription.
9.  Implement the "Restore Purchases" functionality.

**Verification Step (CRITICAL):** After generating the code/solution for this task, **you must verify your work**:
1.  **Check against Acceptance Criteria:** Can the user initiate a purchase flow (F6.1 AC 1)? Does successful purchase update `users.isPremium` and unlock features (F6.1 AC 2)? Are purchase errors/cancellations handled (F6.1 AC 3)? Does Restore Purchases work (F6.1 AC 4)?
2.  **Review Test Cases:** Does the flow allow initiating purchase (TC_F6.1_01 - Placeholder)? Does success update DB/UI (TC_F6.1_02 - Placeholder)? Does failure show feedback (TC_F6.1_03 - Placeholder)? Does restore work (TC_F6.1_04 - Placeholder)?
3.  **Validate UI:** Does the Subscription screen clearly show benefits/pricing/CTA? Is success/error feedback provided during the flow?
4.  **Functionality Check:** Walk through purchase flow (using sandbox accounts): Tap Subscribe -> Platform payment sheet appears -> Confirm purchase -> Success callback -> Receipt validation -> DB updated (`isPremium=true`, `subscriptions` doc created) -> UI unlocks features. Test cancellation/failure scenarios. Test Restore Purchases.
5.  **List Assumptions/Issues:** List assumptions about specific subscription product IDs/pricing, receipt validation method (backend strongly recommended), structure of the `subscriptions` collection, and specific error message wording.
"
---

**(Post-MVP Tasks - Outline)**

* Implement Advanced Matching Filters (Premium)
* Implement Read Receipts (Premium)
* Implement Profile Boost (Premium)
* Implement LinkedIn Sign Up/In (F1.13)
* Implement Apple Sign Up/In (F1.12)
* Implement User Reporting Feature (F4.1)
* Implement Blocking Feature (F4.2)
* Refine Matching Algorithm
* Add Skills Editing/Management
* Add Availability Schedule Feature

---
