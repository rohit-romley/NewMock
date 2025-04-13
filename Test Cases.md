# Mockaccino Mobile App - Test Cases v1.0

This document contains test cases derived from the Mockaccino Mobile App User Stories v1.0.

---
**Test Case ID:** TC_F1.1_01
**User Story ID:** F1.1
**Test Case Title:** Verify navigation to Email Sign-up screen
**Priority:** High
**Preconditions:**
    * User has launched the Mockaccino app for the first time or is logged out.
    * User is on the initial app screen showing sign-up/login options.
**Test Steps:**
    1. Observe the initial app screen.
    2. Tap the "Sign Up with Email" option/button.
**Test Data:**
    * N/A
**Expected Results:**
    * The initial screen displays a "Sign Up with Email" option.
    * The user is navigated to a new screen containing the email sign-up form (fields for Full Name, Email, City, Password, Confirm Password, Terms checkbox).
---
**Test Case ID:** TC_F1.1_02
**User Story ID:** F1.1
**Test Case Title:** Verify 'Sign Up' button enabled with valid data
**Priority:** High
**Preconditions:**
    * User is on the email sign-up screen.
    * 'Sign Up' button is initially disabled.
**Test Steps:**
    1. Enter a valid Full Name into the 'Full Name' field.
    2. Enter a valid and unique (not already registered) email address into the 'Email' field.
    3. Enter a valid City into the 'City' field.
    4. Enter a strong password into the 'Password' field.
    5. Enter the same strong password into the 'Confirm Password' field.
    6. Check the 'Accept Terms of Service and Privacy Policy' checkbox.
    7. Observe the state of the 'Sign Up' button.
**Test Data:**
    * Full Name: Test User One
    * Email: unique_valid_email@example.com
    * City: Calgary
    * Password: StrongPassword123!
    * Confirm Password: StrongPassword123!
    * Accept Terms: Checked
**Expected Results:**
    * The 'Sign Up' button becomes enabled after all required valid data is entered and terms are accepted.
---
**Test Case ID:** TC_F1.1_03
**User Story ID:** F1.1
**Test Case Title:** Verify successful Email sign-up and navigation to Role Selection
**Priority:** High
**Preconditions:**
    * User is on the email sign-up screen.
    * All required fields are filled with valid data (as in TC_F1.1_02).
    * The 'Accept Terms' checkbox is checked.
    * The 'Sign Up' button is enabled.
**Test Steps:**
    1. Tap the 'Sign Up' button.
**Test Data:**
    * (Use data from TC_F1.1_02)
**Expected Results:**
    * An account is successfully created for the user.
    * The user is automatically logged into the app.
    * The user is navigated to the next step in the onboarding flow: the "Select Current Role" screen (F1.6).
---
**Test Case ID:** TC_F1.1_04
**User Story ID:** F1.1
**Test Case Title:** Verify error message for existing email during sign-up
**Priority:** High
**Preconditions:**
    * User is on the email sign-up screen.
    * An account associated with `existing_email@example.com` already exists.
**Test Steps:**
    1. Enter a valid Full Name.
    2. Enter the existing email address `existing_email@example.com` into the 'Email' field.
    3. Enter a valid City.
    4. Enter a strong password and confirm it.
    5. Check the 'Accept Terms' checkbox.
    6. Tap the 'Sign Up' button.
**Test Data:**
    * Full Name: Another User
    * Email: existing_email@example.com
    * City: Edmonton
    * Password: StrongPassword123!
    * Confirm Password: StrongPassword123!
    * Accept Terms: Checked
**Expected Results:**
    * An error message "Email already exists" (or similar) is displayed to the user.
    * The account is not created.
    * The user remains on the sign-up screen.
---
**Test Case ID:** TC_F1.1_05
**User Story ID:** F1.1
**Test Case Title:** Verify inline validation error for invalid email format
**Priority:** Medium
**Preconditions:**
    * User is on the email sign-up screen.
**Test Steps:**
    1. Tap into the 'Email' field.
    2. Enter text that is not a valid email format (e.g., "invalid-email").
    3. Tap outside the 'Email' field (move focus to another field or background).
**Test Data:**
    * Email: invalid-email
**Expected Results:**
    * An inline validation error message "Invalid email format" (or similar) is displayed directly below or near the email field.
    * The 'Sign Up' button should remain disabled (or become disabled if other fields were valid).
---
**Test Case ID:** TC_F1.1_06
**User Story ID:** F1.1
**Test Case Title:** Verify error message for mismatching passwords during sign-up
**Priority:** High
**Preconditions:**
    * User is on the email sign-up screen.
    * All other required fields (Full Name, Email, City) are filled with valid data.
    * 'Accept Terms' checkbox is checked.
**Test Steps:**
    1. Enter a strong password into the 'Password' field.
    2. Enter a different password into the 'Confirm Password' field.
    3. Tap the 'Sign Up' button (it might be enabled if inline validation isn't strict, or this check happens on submit).
**Test Data:**
    * Full Name: Test User Mismatch
    * Email: unique_mismatch@example.com
    * City: Vancouver
    * Password: StrongPassword123!
    * Confirm Password: DifferentPassword456?
    * Accept Terms: Checked
**Expected Results:**
    * An error message "Passwords do not match" (or similar) is displayed.
    * The account is not created.
    * The user remains on the sign-up screen.
---
**Test Case ID:** TC_F1.1_07
**User Story ID:** F1.1
**Test Case Title:** Verify error message for not accepting Terms of Service during sign-up
**Priority:** High
**Preconditions:**
    * User is on the email sign-up screen.
    * All required fields (Full Name, Email, City, Password, Confirm Password) are filled with valid data.
    * The 'Accept Terms' checkbox is *unchecked*.
**Test Steps:**
    1. Ensure the 'Accept Terms' checkbox is unchecked.
    2. Tap the 'Sign Up' button.
**Test Data:**
    * Full Name: Test User No Terms
    * Email: unique_noterms@example.com
    * City: Toronto
    * Password: StrongPassword123!
    * Confirm Password: StrongPassword123!
    * Accept Terms: Unchecked
**Expected Results:**
    * An error message "You must accept the Terms of Service" (or similar) is displayed.
    * The account is not created.
    * The user remains on the sign-up screen.
---
**Test Case ID:** TC_F1.2_01
**User Story ID:** F1.2
**Test Case Title:** Verify 'Sign Up' button is disabled when required fields are missing
**Priority:** High
**Preconditions:**
    * User is on the email sign-up screen.
**Test Steps:**
    1. Observe the initial state of the 'Sign Up' button.
    2. Fill in *some* but not all required fields (e.g., only Full Name and Email).
    3. Observe the state of the 'Sign Up' button.
    4. Leave at least one required field empty (e.g., City or Password).
    5. Check the 'Accept Terms' checkbox.
    6. Observe the state of the 'Sign Up' button.
**Test Data:**
    * Full Name: Partial User
    * Email: partial@example.com
    * City: (empty)
    * Password: StrongPassword123!
    * Confirm Password: StrongPassword123!
    * Accept Terms: Checked
**Expected Results:**
    * The 'Sign Up' button is initially disabled.
    * The 'Sign Up' button remains disabled as long as any required field (Full Name, Email, City, Password, Confirm Password) is empty or invalid, or if Terms are not accepted.
---
**Test Case ID:** TC_F1.2_02
**User Story ID:** F1.2
**Test Case Title:** Verify profile picture upload prompt appears
**Priority:** Medium
**Preconditions:**
    * User is on the email sign-up screen.
    * A placeholder image/icon for the profile picture is visible.
**Test Steps:**
    1. Tap on the profile picture placeholder area.
**Test Data:**
    * N/A
**Expected Results:**
    * A system prompt or menu appears asking the user to choose an image source (e.g., "Take Photo", "Choose from Library/Gallery").
---
**Test Case ID:** TC_F1.2_03
**User Story ID:** F1.2
**Test Case Title:** Verify successfully uploaded profile picture is displayed on sign-up form
**Priority:** Medium
**Preconditions:**
    * User is on the email sign-up screen.
    * User has tapped the profile picture placeholder and the image source selection prompt is visible.
    * User has access to photos in their device library/gallery or can use the camera.
**Test Steps:**
    1. Select an image source (e.g., "Choose from Library").
    2. Select a valid image file.
    3. Confirm the selection (if prompted for cropping/editing, complete that step).
    4. Observe the profile picture area on the sign-up form.
**Test Data:**
    * Image: A standard image file (e.g., JPG, PNG) from the device.
**Expected Results:**
    * The selected image is displayed in the profile picture area on the sign-up form, replacing the placeholder.
---
**Test Case ID:** TC_F1.2_04
**User Story ID:** F1.2
**Test Case Title:** Verify successful sign-up without uploading profile picture uses default image
**Priority:** Medium
**Preconditions:**
    * User is on the email sign-up screen.
    * All required text fields are filled with valid data.
    * The 'Accept Terms' checkbox is checked.
    * The user has *not* uploaded a profile picture (the placeholder is still shown).
**Test Steps:**
    1. Tap the 'Sign Up' button.
    2. Proceed through onboarding (F1.6, F1.7) until reaching the main app or profile screen (F1.8).
    3. Navigate to the user's profile screen (F1.8).
    4. Observe the profile picture area.
**Test Data:**
    * (Use data similar to TC_F1.1_02, but do not upload a picture)
    * Full Name: Default Pic User
    * Email: default_pic@example.com
    * City: Calgary
    * Password: StrongPassword123!
    * Confirm Password: StrongPassword123!
    * Accept Terms: Checked
**Expected Results:**
    * Sign-up is successful.
    * On the user's profile screen (F1.8), a default profile picture or placeholder image is displayed.
---
**Test Case ID:** TC_F1.2_05
**User Story ID:** F1.2
**Test Case Title:** Verify required fields (Name, City) are stored after successful sign-up
**Priority:** High
**Preconditions:**
    * User successfully completes the sign-up process (e.g., following steps of TC_F1.1_03 or TC_F1.2_04).
    * User completes onboarding (F1.6, F1.7).
**Test Steps:**
    1. Navigate to the user's profile screen (F1.8).
    2. Observe the displayed Full Name and City.
**Test Data:**
    * (Data entered during sign-up, e.g., Full Name: 'Test User One', City: 'Calgary')
**Expected Results:**
    * The Full Name displayed on the profile screen matches the Full Name entered during sign-up.
    * The City displayed on the profile screen matches the City entered during sign-up.
    * (Email is not typically displayed directly on the profile for privacy, but is stored).
---
**Test Case ID:** TC_F1.3_01
**User Story ID:** F1.3
**Test Case Title:** Verify visibility of 'Accept Terms' checkbox and links
**Priority:** High
**Preconditions:**
    * User is on the email sign-up screen (F1.1) or any other sign-up screen requiring terms acceptance.
**Test Steps:**
    1. Observe the sign-up form near the 'Sign Up' button.
**Test Data:**
    * N/A
**Expected Results:**
    * A checkbox or toggle element is visible.
    * Text associated with the checkbox includes "I accept the Terms of Service and Privacy Policy" (or similar).
    * The phrases "Terms of Service" and "Privacy Policy" within the text are presented as tappable links.
---
**Test Case ID:** TC_F1.3_02
**User Story ID:** F1.3
**Test Case Title:** Verify tapping 'Terms of Service' link displays the document
**Priority:** Medium
**Preconditions:**
    * User is on the sign-up screen where the 'Accept Terms' checkbox and links are visible.
**Test Steps:**
    1. Tap the "Terms of Service" link.
**Test Data:**
    * N/A
**Expected Results:**
    * The Terms of Service document is displayed to the user (e.g., within an in-app webview, or by opening the device's web browser).
    * The user can view the content of the Terms of Service.
---
**Test Case ID:** TC_F1.3_03
**User Story ID:** F1.3
**Test Case Title:** Verify tapping 'Privacy Policy' link displays the document
**Priority:** Medium
**Preconditions:**
    * User is on the sign-up screen where the 'Accept Terms' checkbox and links are visible.
**Test Steps:**
    1. Tap the "Privacy Policy" link.
**Test Data:**
    * N/A
**Expected Results:**
    * The Privacy Policy document is displayed to the user (e.g., within an in-app webview, or by opening the device's web browser).
    * The user can view the content of the Privacy Policy.
---
**Test Case ID:** TC_F1.3_04
**User Story ID:** F1.3
**Test Case Title:** Verify 'Sign Up' button remains disabled or shows error if 'Accept Terms' is unchecked
**Priority:** High
**Preconditions:**
    * User is on the email sign-up screen.
    * All required fields (Full Name, Email, City, Password, Confirm Password) are filled with valid data.
    * The 'Accept Terms' checkbox is *unchecked*.
**Test Steps:**
    1. Observe the state of the 'Sign Up' button.
    2. Tap the 'Sign Up' button.
**Test Data:**
    * (Use data from TC_F1.1_07)
**Expected Results:**
    * The 'Sign Up' button is disabled.
    * OR, if the button is enabled, tapping it displays an error message "You must accept the Terms of Service" (or similar) and does not proceed with sign-up.
---
**Test Case ID:** TC_F1.3_05
**User Story ID:** F1.3
**Test Case Title:** Verify 'Sign Up' button becomes enabled when 'Accept Terms' is checked (assuming other fields are valid)
**Priority:** High
**Preconditions:**
    * User is on the email sign-up screen.
    * All required fields (Full Name, Email, City, Password, Confirm Password) are filled with valid data.
    * The 'Accept Terms' checkbox is initially *unchecked*.
    * The 'Sign Up' button is disabled.
**Test Steps:**
    1. Check the 'Accept Terms' checkbox.
    2. Observe the state of the 'Sign Up' button.
**Test Data:**
    * (Use data from TC_F1.1_02, but start with checkbox unchecked)
**Expected Results:**
    * The 'Sign Up' button becomes enabled immediately after the 'Accept Terms' checkbox is checked (given all other fields are valid).
---
**Test Case ID:** TC_F1.4_01
**User Story ID:** F1.4
**Test Case Title:** Verify navigation to Email/Password Login screen
**Priority:** High
**Preconditions:**
    * User has launched the Mockaccino app.
    * User is on the initial app screen showing sign-up/login options.
**Test Steps:**
    1. Observe the initial app screen.
    2. Tap the "Log In" option/button.
**Test Data:**
    * N/A
**Expected Results:**
    * The initial screen displays a "Log In" option.
    * The user is navigated to a new screen containing the email/password login form (fields for Email, Password, "Forgot Password?" link, 'Log In' button).
---
**Test Case ID:** TC_F1.4_02
**User Story ID:** F1.4
**Test Case Title:** Verify 'Log In' button enabled with registered email and password entered
**Priority:** High
**Preconditions:**
    * User is on the email/password login screen.
    * 'Log In' button may be initially disabled or enabled.
**Test Steps:**
    1. Enter a registered email address into the 'Email' field.
    2. Enter the corresponding password into the 'Password' field.
    3. Observe the state of the 'Log In' button.
**Test Data:**
    * Email: registered_user@example.com
    * Password: CorrectPassword123!
**Expected Results:**
    * The 'Log In' button is enabled after both the email and password fields contain text. (Exact behavior depends on implementation - could be enabled once both fields have any text, or only after validation attempt).
---
**Test Case ID:** TC_F1.4_03
**User Story ID:** F1.4
**Test Case Title:** Verify successful login with correct credentials navigates to the main matching screen
**Priority:** High
**Preconditions:**
    * User is on the email/password login screen.
    * User has an existing account created via email sign-up (F1.1).
**Test Steps:**
    1. Enter the registered email address into the 'Email' field.
    2. Enter the correct password associated with that email into the 'Password' field.
    3. Tap the 'Log In' button.
**Test Data:**
    * Email: registered_user@example.com
    * Password: CorrectPassword123!
**Expected Results:**
    * The user is successfully authenticated.
    * The user is navigated away from the login screen to the main matching screen (F2.1).
---
**Test Case ID:** TC_F1.4_04
**User Story ID:** F1.4
**Test Case Title:** Verify error message for login attempt with incorrect password
**Priority:** High
**Preconditions:**
    * User is on the email/password login screen.
    * User has an existing account with email `registered_user@example.com`.
**Test Steps:**
    1. Enter the registered email address `registered_user@example.com` into the 'Email' field.
    2. Enter an incorrect password into the 'Password' field.
    3. Tap the 'Log In' button.
**Test Data:**
    * Email: registered_user@example.com
    * Password: IncorrectPassword456?
**Expected Results:**
    * An error message "Invalid email or password" (or similar) is displayed.
    * The user remains on the login screen.
---
**Test Case ID:** TC_F1.4_05
**User Story ID:** F1.4
**Test Case Title:** Verify error message for login attempt with unregistered email
**Priority:** High
**Preconditions:**
    * User is on the email/password login screen.
    * No account exists with the email `unregistered_user@example.com`.
**Test Steps:**
    1. Enter the unregistered email address `unregistered_user@example.com` into the 'Email' field.
    2. Enter any password into the 'Password' field.
    3. Tap the 'Log In' button.
**Test Data:**
    * Email: unregistered_user@example.com
    * Password: AnyPassword123
**Expected Results:**
    * An error message "Invalid email or password" (or similar, potentially identical to incorrect password error for security) is displayed.
    * The user remains on the login screen.
---
**Test Case ID:** TC_F1.5_01
**User Story ID:** F1.5
**Test Case Title:** Verify navigation to Password Reset request screen via "Forgot Password?" link
**Priority:** Medium
**Preconditions:**
    * User is on the email/password login screen (F1.4).
    * A "Forgot Password?" link is visible.
**Test Steps:**
    1. Tap the "Forgot Password?" link.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is navigated to a new screen designed for requesting a password reset.
    * This screen contains an input field for the user's email address and a button like "Send Reset Link".
---
**Test Case ID:** TC_F1.5_02
**User Story ID:** F1.5
**Test Case Title:** Verify confirmation message and email sent after requesting reset for a registered email
**Priority:** High
**Preconditions:**
    * User is on the password reset request screen.
    * An account exists with the email `registered_user_forgot@example.com`.
    * Email sending service is functional.
**Test Steps:**
    1. Enter the registered email address `registered_user_forgot@example.com` into the email field.
    2. Tap the "Send Reset Link" button.
    3. Check the inbox for `registered_user_forgot@example.com`.
**Test Data:**
    * Email: registered_user_forgot@example.com
**Expected Results:**
    * A confirmation message is displayed on the screen (e.g., "Password reset instructions sent to your email.").
    * An email containing a unique password reset link is delivered to `registered_user_forgot@example.com`.
---
**Test Case ID:** TC_F1.5_03
**User Story ID:** F1.5
**Test Case Title:** Verify clicking the valid reset link navigates to the new password entry page
**Priority:** High
**Preconditions:**
    * User has received a valid password reset email (from TC_F1.5_02).
    * The reset link has not expired.
**Test Steps:**
    1. Open the password reset email.
    2. Click or tap the password reset link within the email.
**Test Data:**
    * Valid, non-expired password reset link.
**Expected Results:**
    * The user is taken to a secure page (either within the app via deep linking, or in a web browser).
    * This page contains fields for entering a new password and confirming the new password, along with a "Reset Password" or "Save" button.
---
**Test Case ID:** TC_F1.5_04
**User Story ID:** F1.5
**Test Case Title:** Verify successful password reset with valid new password
**Priority:** High
**Preconditions:**
    * User is on the new password entry page (navigated via a valid reset link).
**Test Steps:**
    1. Enter a new strong password into the 'New Password' field.
    2. Enter the same new strong password into the 'Confirm New Password' field.
    3. Tap the "Reset Password" or "Save" button.
    4. Attempt to log in (F1.4) using the original email and the *new* password.
**Test Data:**
    * New Password: NewStrongPassword456!
    * Confirm New Password: NewStrongPassword456!
    * Email (for login): registered_user_forgot@example.com
**Expected Results:**
    * A success message is displayed (e.g., "Password successfully updated.").
    * The user's account password is changed in the system.
    * The user can successfully log in using the email and the newly set password.
    * The password reset link used becomes invalid.
---
**Test Case ID:** TC_F1.5_05
**User Story ID:** F1.5
**Test Case Title:** Verify error message when requesting password reset for an unregistered email
**Priority:** Medium
**Preconditions:**
    * User is on the password reset request screen.
    * No account exists with the email `unregistered_forgot@example.com`.
**Test Steps:**
    1. Enter the unregistered email address `unregistered_forgot@example.com` into the email field.
    2. Tap the "Send Reset Link" button.
**Test Data:**
    * Email: unregistered_forgot@example.com
**Expected Results:**
    * An error message is displayed (e.g., "Email not found", or potentially a generic message like "If an account exists for this email, reset instructions have been sent" for security).
    * No password reset email is sent.
---
**Test Case ID:** TC_F1.5_06
**User Story ID:** F1.5
**Test Case Title:** Verify error message when accessing an invalid or expired password reset link
**Priority:** Medium
**Preconditions:**
    * User attempts to access a password reset link that is either expired (past its time limit) or has already been used, or is malformed.
**Test Steps:**
    1. Click or tap on an invalid/expired password reset link.
**Test Data:**
    * Expired/Used/Malformed password reset link.
**Expected Results:**
    * The user is navigated to a page displaying an error message.
    * The error message indicates that the link is invalid or expired (e.g., "Password reset link is invalid or has expired.").
    * The user is not presented with the fields to enter a new password.
---
**Test Case ID:** TC_F1.6_01
**User Story ID:** F1.6
**Test Case Title:** Verify navigation to "Current Role" selection screen after sign-up/first SSO login
**Priority:** High
**Preconditions:**
    * User has just successfully completed sign-up (Email F1.1, Apple F1.12, or LinkedIn F1.13).
    * OR User has just logged in for the first time using SSO (Apple F1.14, LinkedIn F1.14) and onboarding is required.
**Test Steps:**
    1. Complete the sign-up or initial SSO login process.
    2. Observe the screen presented immediately after authentication/account creation.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is automatically navigated to the "Select Current Role" screen as the first step of the onboarding process.
    * The screen prompts the user to select their current job role.
---
**Test Case ID:** TC_F1.6_02
**User Story ID:** F1.6
**Test Case Title:** Verify selection of "Current Role"
**Priority:** High
**Preconditions:**
    * User is on the "Current Role" selection screen during onboarding.
    * A list of predefined roles is available (potentially with search).
**Test Steps:**
    1. Search for or scroll to find a desired role (e.g., "Software Engineer").
    2. Select the desired role from the list.
    3. Tap the "Next" or "Continue" button (if roles are on separate screens).
**Test Data:**
    * Selected Current Role: Software Engineer
**Expected Results:**
    * The selected role ("Software Engineer") is registered/acknowledged by the UI.
    * The user proceeds to the next step (either "Target Role" selection or a combined next step).
---
**Test Case ID:** TC_F1.6_03
**User Story ID:** F1.6
**Test Case Title:** Verify navigation to "Target Role" selection screen
**Priority:** High
**Preconditions:**
    * User is on the "Current Role" selection screen during onboarding.
    * User has selected a Current Role.
    * Roles are selected on separate screens.
**Test Steps:**
    1. Select a Current Role.
    2. Tap the "Next" or "Continue" button.
**Test Data:**
    * Selected Current Role: Software Engineer
**Expected Results:**
    * The user is navigated to the "Select Target Role" screen.
    * The screen prompts the user to select their target job role.
---
**Test Case ID:** TC_F1.6_04
**User Story ID:** F1.6
**Test Case Title:** Verify selection of "Target Role"
**Priority:** High
**Preconditions:**
    * User is on the "Target Role" selection screen during onboarding.
    * A list of predefined roles is available (potentially with search).
**Test Steps:**
    1. Search for or scroll to find a desired role (e.g., "Senior Software Engineer").
    2. Select the desired role from the list.
**Test Data:**
    * Selected Target Role: Senior Software Engineer
**Expected Results:**
    * The selected role ("Senior Software Engineer") is registered/acknowledged by the UI.
---
**Test Case ID:** TC_F1.6_05
**User Story ID:** F1.6
**Test Case Title:** Verify saving selected roles and navigation to "Interaction Preference" screen (F1.7)
**Priority:** High
**Preconditions:**
    * User is on the final role selection step during onboarding (either combined or the Target Role screen).
    * User has selected both a Current Role and a Target Role.
**Test Steps:**
    1. Ensure both Current Role and Target Role are selected.
    2. Tap the "Next" or "Continue" button.
**Test Data:**
    * Selected Current Role: Software Engineer
    * Selected Target Role: Senior Software Engineer
**Expected Results:**
    * The selected Current Role and Target Role are saved to the user's profile (verified later in F1.8).
    * The user is navigated to the next onboarding step: the "Select Interaction Preference" screen (F1.7).
---
**Test Case ID:** TC_F1.7_01
**User Story ID:** F1.7
**Test Case Title:** Verify navigation to "Interaction Preference" screen after role selection
**Priority:** High
**Preconditions:**
    * User has successfully completed the role selection step (F1.6) during onboarding.
**Test Steps:**
    1. Complete the role selection step(s).
    2. Tap "Next" or "Continue" on the final role selection screen.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is navigated to the "Interaction Preference" screen.
    * The screen presents options like "Referral Exchange", "Mock Interviews", and "Both".
---
**Test Case ID:** TC_F1.7_02
**User Story ID:** F1.7
**Test Case Title:** Verify selection of interaction preference (Referral Exchange)
**Priority:** Medium
**Preconditions:**
    * User is on the "Interaction Preference" screen during onboarding.
**Test Steps:**
    1. Select the "Referral Exchange" option.
    2. Observe the UI acknowledges the selection.
**Test Data:**
    * Selection: Referral Exchange
**Expected Results:**
    * The "Referral Exchange" option is visually selected (e.g., radio button checked, button highlighted).
---
**Test Case ID:** TC_F1.7_03
**User Story ID:** F1.7
**Test Case Title:** Verify selection of interaction preference (Mock Interviews)
**Priority:** Medium
**Preconditions:**
    * User is on the "Interaction Preference" screen during onboarding.
**Test Steps:**
    1. Select the "Mock Interviews" option.
    2. Observe the UI acknowledges the selection.
**Test Data:**
    * Selection: Mock Interviews
**Expected Results:**
    * The "Mock Interviews" option is visually selected.
---
**Test Case ID:** TC_F1.7_04
**User Story ID:** F1.7
**Test Case Title:** Verify selection of interaction preference (Both)
**Priority:** Medium
**Preconditions:**
    * User is on the "Interaction Preference" screen during onboarding.
**Test Steps:**
    1. Select the "Both" option.
    2. Observe the UI acknowledges the selection.
**Test Data:**
    * Selection: Both
**Expected Results:**
    * The "Both" option is visually selected.
---
**Test Case ID:** TC_F1.7_05
**User Story ID:** F1.7
**Test Case Title:** Verify saving preference and navigation to the main matching screen (F2.1)
**Priority:** High
**Preconditions:**
    * User is on the "Interaction Preference" screen during onboarding.
    * User has selected one of the preferences ("Referral Exchange", "Mock Interviews", or "Both").
**Test Steps:**
    1. Ensure an interaction preference is selected.
    2. Tap the "Finish", "Done", or "Continue" button.
**Test Data:**
    * Selection: (Any of the three options)
**Expected Results:**
    * The selected interaction preference is saved to the user's profile (verified later in F1.8).
    * The onboarding process is complete.
    * The user is navigated to the main matching screen (F2.1).
---
**Test Case ID:** TC_F1.8_01
**User Story ID:** F1.8
**Test Case Title:** Verify own profile screen displays correct initial data after onboarding
**Priority:** High
**Preconditions:**
    * User has completed sign-up and onboarding (F1.1-F1.7).
    * User is logged in.
**Test Steps:**
    1. Navigate to the user's own profile screen (e.g., via a "Profile" tab or menu).
    2. Observe the displayed Profile Picture.
    3. Observe the displayed Full Name.
    4. Observe the displayed Location (City).
    5. Observe the displayed Current Role.
    6. Observe the displayed Target Role.
    7. Observe the displayed Bio section.
    8. Observe the displayed Interaction Preference.
**Test Data:**
    * Data entered/selected during Sign Up & Onboarding:
        * Profile Picture: (Uploaded image or Default image)
        * Full Name: Test User One
        * City: Calgary
        * Current Role: Software Engineer
        * Target Role: Senior Software Engineer
        * Bio: (Should be empty or show placeholder text)
        * Interaction Preference: Both
**Expected Results:**
    * The Profile Picture matches the uploaded image or the default image if none was uploaded.
    * The Full Name matches the name entered during sign-up.
    * The Location (City) matches the city entered during sign-up.
    * The Current Role matches the role selected during onboarding.
    * The Target Role matches the role selected during onboarding.
    * The Bio section is empty or displays placeholder text (e.g., "Tap to add a bio").
    * The Interaction Preference matches the preference selected during onboarding.
---
**Test Case ID:** TC_F1.8_02
**User Story ID:** F1.8
**Test Case Title:** Verify viewing another user's profile (post-match) displays their information
**Priority:** Medium
**Preconditions:**
    * User A is logged in.
    * User A has matched with User B (F2.4).
    * User B has completed their profile (Photo, Name, City, Roles, Bio, Preference).
**Test Steps:**
    1. Navigate to the chat screen with User B (e.g., from the "It's a Match!" screen or the Chats list F3.1).
    2. From the chat screen, tap on User B's name or profile picture to view their profile.
    3. Observe User B's profile screen.
**Test Data:**
    * User B's Profile Data:
        * Photo: User B's photo
        * Name: User B Name
        * City: User B City
        * Current Role: User B Current Role
        * Target Role: User B Target Role
        * Bio: User B Bio Text
        * Preference: User B Preference
**Expected Results:**
    * User B's profile screen is displayed.
    * The screen correctly shows User B's Photo, Name, City, Current Role, Target Role, Bio, and Interaction Preference.
---
**Test Case ID:** TC_F1.9_01
**User Story ID:** F1.9
**Test Case Title:** Verify entering profile edit mode from own profile view
**Priority:** High
**Preconditions:**
    * User is logged in.
    * User is viewing their own profile screen (F1.8).
**Test Steps:**
    1. Locate and tap the "Edit Profile" button or icon.
**Test Data:**
    * N/A
**Expected Results:**
    * The profile screen transitions into an editable state.
    * Fields like Name, City, Bio become editable text inputs.
    * Options to change Photo, Roles, and Interaction Preference become apparent (e.g., tappable elements, specific buttons).
    * "Save" and "Cancel" (or similar) buttons appear.
---
**Test Case ID:** TC_F1.9_02
**User Story ID:** F1.9
**Test Case Title:** Verify editing and saving Full Name, City, and Bio text fields
**Priority:** High
**Preconditions:**
    * User is in profile edit mode (TC_F1.9_01).
**Test Steps:**
    1. Modify the text in the 'Full Name' input field.
    2. Modify the text in the 'City' input field.
    3. Modify the text in the 'Bio' input field.
    4. Tap the "Save" button.
    5. Observe the profile screen (now in view mode).
**Test Data:**
    * New Full Name: Updated Test User
    * New City: Updated City
    * New Bio: This is my updated bio text.
**Expected Results:**
    * The profile returns to view mode.
    * The displayed Full Name, City, and Bio reflect the changes made in the edit mode.
    * The changes persist after leaving and returning to the profile screen.
---
**Test Case ID:** TC_F1.9_03
**User Story ID:** F1.9
**Test Case Title:** Verify changing Profile Picture and saving
**Priority:** Medium
**Preconditions:**
    * User is in profile edit mode (TC_F1.9_01).
**Test Steps:**
    1. Tap on the current profile picture or a "Change Picture" button/icon.
    2. Select a new image source (camera or gallery).
    3. Choose/take a new image.
    4. Confirm the new image selection (complete cropping/editing if applicable).
    5. Tap the "Save" button on the profile edit screen.
    6. Observe the profile screen (now in view mode).
**Test Data:**
    * New Image: A different valid image file.
**Expected Results:**
    * The profile returns to view mode.
    * The newly uploaded image is displayed as the profile picture.
    * The change persists after leaving and returning to the profile screen.
---
**Test Case ID:** TC_F1.9_04
**User Story ID:** F1.9
**Test Case Title:** Verify changing Current Role and Target Role and saving
**Priority:** Medium
**Preconditions:**
    * User is in profile edit mode (TC_F1.9_01).
**Test Steps:**
    1. Tap on the Current Role field or a "Change Role" button.
    2. Select a new Current Role from the presented list/search.
    3. Tap on the Target Role field or a "Change Role" button.
    4. Select a new Target Role from the presented list/search.
    5. Tap the "Save" button on the profile edit screen.
    6. Observe the profile screen (now in view mode).
**Test Data:**
    * New Current Role: Product Manager
    * New Target Role: Director of Product
**Expected Results:**
    * The profile returns to view mode.
    * The displayed Current Role and Target Role reflect the new selections.
    * The changes persist after leaving and returning to the profile screen.
---
**Test Case ID:** TC_F1.9_05
**User Story ID:** F1.9
**Test Case Title:** Verify changing Interaction Preference and saving
**Priority:** Medium
**Preconditions:**
    * User is in profile edit mode (TC_F1.9_01).
**Test Steps:**
    1. Tap on the Interaction Preference field or a "Change Preference" button.
    2. Select a new preference (e.g., "Mock Interviews" if it was previously "Both").
    3. Tap the "Save" button on the profile edit screen.
    4. Observe the profile screen (now in view mode).
**Test Data:**
    * New Interaction Preference: Mock Interviews
**Expected Results:**
    * The profile returns to view mode.
    * The displayed Interaction Preference reflects the new selection.
    * The change persists after leaving and returning to the profile screen.
---
**Test Case ID:** TC_F1.9_06
**User Story ID:** F1.9
**Test Case Title:** Verify prompt to save or discard changes appears when navigating away from edit mode after making changes
**Priority:** Medium
**Preconditions:**
    * User is in profile edit mode (TC_F1.9_01).
    * User has made at least one change to a profile field (e.g., edited Bio).
**Test Steps:**
    1. Make a change to a profile field (e.g., edit the Bio).
    2. Attempt to navigate away from the edit screen without tapping "Save" (e.g., tap the back button, switch tabs).
**Test Data:**
    * Edited Bio: Temporary change.
**Expected Results:**
    * A confirmation prompt/dialog appears.
    * The prompt asks the user if they want to save the changes or discard them (e.g., "Discard changes?", with options like "Save", "Discard", "Cancel").
---
**Test Case ID:** TC_F1.9_07
**User Story ID:** F1.9
**Test Case Title:** Verify discarding changes reverts profile to original state
**Priority:** Medium
**Preconditions:**
    * User is in profile edit mode (TC_F1.9_01).
    * User has made at least one change to a profile field.
    * User attempts to navigate away and the save/discard prompt (TC_F1.9_06) is displayed.
**Test Steps:**
    1. In the save/discard prompt, tap the "Discard" option.
    2. Observe the profile screen (now in view mode).
**Test Data:**
    * Original Bio: My original bio.
    * Edited Bio (before discard): Temporary change.
**Expected Results:**
    * The user is navigated away from the edit mode (or returned to view mode).
    * The profile fields display the data as it was *before* entering edit mode (the changes were not saved).
---
**Test Case ID:** TC_F1.10_01
**User Story ID:** F1.10
**Test Case Title:** Verify "Log Out" option is available in the Settings screen
**Priority:** High
**Preconditions:**
    * User is logged into the app.
**Test Steps:**
    1. Navigate to the main Settings screen (F5.1).
    2. Scan the options available on the Settings screen.
**Test Data:**
    * N/A
**Expected Results:**
    * A "Log Out" button or menu item is clearly visible on the Settings screen.
---
**Test Case ID:** TC_F1.10_02
**User Story ID:** F1.10
**Test Case Title:** Verify confirmation prompt appears upon tapping "Log Out"
**Priority:** High
**Preconditions:**
    * User is logged in.
    * User is on the Settings screen (F5.1).
    * The "Log Out" option is visible.
**Test Steps:**
    1. Tap the "Log Out" option.
**Test Data:**
    * N/A
**Expected Results:**
    * A confirmation dialog/alert appears.
    * The dialog asks the user to confirm the action (e.g., "Are you sure you want to log out?").
    * The dialog presents options like "Log Out" / "Yes" and "Cancel" / "No".
---
**Test Case ID:** TC_F1.10_03
**User Story ID:** F1.10
**Test Case Title:** Verify confirming logout terminates session and returns user to the initial sign-up/login screen
**Priority:** High
**Preconditions:**
    * User is logged in.
    * User has tapped "Log Out" and the confirmation prompt is displayed (TC_F1.10_02).
**Test Steps:**
    1. Tap the "Log Out" or "Yes" option in the confirmation dialog.
**Test Data:**
    * N/A
**Expected Results:**
    * The user's session is terminated (local tokens/data cleared).
    * The user is navigated away from the settings/main app screen.
    * The user is presented with the initial sign-up/login screen of the app.
---
**Test Case ID:** TC_F1.10_04
**User Story ID:** F1.10
**Test Case Title:** Verify relaunching the app after logout presents the sign-up/login screen
**Priority:** High
**Preconditions:**
    * User has successfully logged out (TC_F1.10_03).
    * User has closed the app.
**Test Steps:**
    1. Relaunch the Mockaccino app.
**Test Data:**
    * N/A
**Expected Results:**
    * The app opens to the initial sign-up/login screen.
    * The user is not automatically logged into their previous account.
---
**Test Case ID:** TC_F1.11_01
**User Story ID:** F1.11
**Test Case Title:** Verify "Deactivate Account" option is available within Settings
**Priority:** Low
**Preconditions:**
    * User is logged in.
    * The Deactivate Account feature (F1.11) has been implemented.
**Test Steps:**
    1. Navigate to the main Settings screen (F5.1).
    2. Look for an "Account Settings" or similar section.
    3. Within that section, look for a "Deactivate Account" option.
**Test Data:**
    * N/A
**Expected Results:**
    * A "Deactivate Account" option/link is visible within the Settings screen, likely under an "Account" subsection.
---
**Test Case ID:** TC_F1.11_02
**User Story ID:** F1.11
**Test Case Title:** Verify information/warning and confirmation step are presented upon initiating deactivation
**Priority:** Low
**Preconditions:**
    * User is logged in.
    * User is on the Settings screen and the "Deactivate Account" option is visible.
**Test Steps:**
    1. Tap the "Deactivate Account" option.
**Test Data:**
    * N/A
**Expected Results:**
    * A new screen or dialog appears.
    * This view explains the consequences of deactivating the account (e.g., profile hidden, matches removed, eventual data deletion per policy).
    * A clear confirmation step is required (e.g., a button labeled "Confirm Deactivation", potentially requiring password re-entry).
---
**Test Case ID:** TC_F1.11_03
**User Story ID:** F1.11
**Test Case Title:** Verify confirming deactivation marks account inactive, hides profile, and logs the user out
**Priority:** Low
**Preconditions:**
    * User is logged in.
    * User has initiated the deactivation process and the confirmation view (TC_F1.11_02) is displayed.
    * (Requires a second test account, User B, to verify profile hiding).
**Test Steps:**
    1. Confirm the deactivation request (e.g., tap "Confirm Deactivation", enter password if required).
    2. Observe the app's behavior immediately after confirmation.
    3. Using User B's account, attempt to find User A's profile (e.g., through matching if filters allow, or search if implemented).
**Test Data:**
    * User A's credentials.
    * User B's credentials.
**Expected Results:**
    * User A's account is marked as inactive in the backend.
    * User A is immediately logged out of the app and returned to the sign-up/login screen.
    * User B can no longer find User A's profile through matching or other discovery methods.
---
**Test Case ID:** TC_F1.11_04
**User Story ID:** F1.11
**Test Case Title:** Verify attempting to log in with deactivated account credentials shows an appropriate error message
**Priority:** Low
**Preconditions:**
    * User A's account has been deactivated (TC_F1.11_03).
    * User A is on the login screen.
**Test Steps:**
    1. Enter the email address associated with the deactivated account (User A).
    2. Enter the last known password for the deactivated account.
    3. Tap the "Log In" button.
**Test Data:**
    * User A's email (deactivated).
    * User A's password.
**Expected Results:**
    * An error message is displayed indicating the account is inactive or cannot be found (e.g., "Account deactivated" or "Invalid email or password").
    * Login is unsuccessful.
---
**Test Case ID:** TC_F1.12_01
**User Story ID:** F1.12
**Test Case Title:** Verify tapping "Sign Up with Apple" initiates the native Apple Sign-In flow
**Priority:** Medium
**Preconditions:**
    * User is on the initial app screen showing sign-up/login options.
    * User is using an iOS device with Apple Sign-In configured.
    * "Sign Up with Apple" button is visible.
**Test Steps:**
    1. Tap the "Sign Up with Apple" button.
**Test Data:**
    * N/A
**Expected Results:**
    * The native iOS Apple Sign-In sheet/prompt appears, asking the user to authenticate using Face ID, Touch ID, or passcode.
---
**Test Case ID:** TC_F1.12_02
**User Story ID:** F1.12
**Test Case Title:** Verify successful Apple Sign-In creates a Mockaccino account
**Priority:** Medium
**Preconditions:**
    * User is on the initial app screen.
    * User initiates Apple Sign-In (TC_F1.12_01).
    * User successfully authenticates with Apple.
**Test Steps:**
    1. Complete the Apple Sign-In authentication flow (including choosing whether to share email).
**Test Data:**
    * Apple ID credentials.
**Expected Results:**
    * A new Mockaccino account is created, associated with the user's Apple ID (and potentially the shared or private relay email).
    * The user is logged into the Mockaccino app.
---
**Test Case ID:** TC_F1.12_03
**User Story ID:** F1.12
**Test Case Title:** Verify user is logged in and navigated to Role Selection (F1.6) after successful Apple Sign-Up
**Priority:** Medium
**Preconditions:**
    * User has successfully created an account via Apple Sign-In (TC_F1.12_02).
**Test Steps:**
    1. Observe the screen presented immediately after successful Apple Sign-In and account creation.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is automatically navigated to the "Select Current Role" screen (F1.6) as the first step of the onboarding process.
---
**Test Case ID:** TC_F1.12_04
**User Story ID:** F1.12
**Test Case Title:** Verify profile information (Name, Email if shared) is pre-filled based on Apple Sign-In data
**Priority:** Low
**Preconditions:**
    * User created an account via Apple Sign-In, sharing their real email.
    * User has completed onboarding (F1.6, F1.7).
**Test Steps:**
    1. Navigate to the user's profile screen (F1.8).
    2. Observe the Full Name field.
    3. (If applicable) Navigate to account settings where email might be displayed.
**Test Data:**
    * Name associated with Apple ID.
    * Real email shared via Apple Sign-In.
**Expected Results:**
    * The Full Name on the profile matches the name provided by Apple Sign-In.
    * The email associated with the account matches the real email shared during sign-up.
---
**Test Case ID:** TC_F1.12_05
**User Story ID:** F1.12
**Test Case Title:** Verify handling of hidden email scenario during Apple Sign-Up
**Priority:** Low
**Preconditions:**
    * User initiates Apple Sign-In (TC_F1.12_01).
    * User chooses the "Hide My Email" option during the Apple Sign-In flow.
    * User successfully authenticates.
**Test Steps:**
    1. Complete the Apple Sign-In flow, selecting "Hide My Email".
    2. Proceed through onboarding.
    3. (If applicable) Navigate to account settings where email might be displayed.
**Test Data:**
    * Apple ID credentials.
    * Selection: Hide My Email
**Expected Results:**
    * A Mockaccino account is created successfully.
    * The email associated with the account is the private relay email address provided by Apple, not the user's real email address.
---
**Test Case ID:** TC_F1.13_01
**User Story ID:** F1.13
**Test Case Title:** Verify tapping "Sign Up with LinkedIn" initiates the LinkedIn OAuth flow
**Priority:** Medium
**Preconditions:**
    * User is on the initial app screen showing sign-up/login options.
    * "Sign Up with LinkedIn" button is visible.
    * User has the LinkedIn app installed or is prepared to log in via web view.
**Test Steps:**
    1. Tap the "Sign Up with LinkedIn" button.
**Test Data:**
    * N/A
**Expected Results:**
    * The app transitions to the LinkedIn authentication flow (either switching to the LinkedIn app or opening a web view).
    * The user is prompted to log into LinkedIn (if not already) and authorize the Mockaccino app to access requested permissions (e.g., basic profile, email).
---
**Test Case ID:** TC_F1.13_02
**User Story ID:** F1.13
**Test Case Title:** Verify successful LinkedIn authentication creates a Mockaccino account
**Priority:** Medium
**Preconditions:**
    * User is on the initial app screen.
    * User initiates LinkedIn Sign-In (TC_F1.13_01).
    * User successfully authenticates with LinkedIn and grants permissions.
**Test Steps:**
    1. Complete the LinkedIn authentication and authorization flow.
**Test Data:**
    * LinkedIn credentials.
**Expected Results:**
    * A new Mockaccino account is created, associated with the user's LinkedIn profile data (Name, Email, etc., based on granted permissions).
    * The user is logged into the Mockaccino app.
---
**Test Case ID:** TC_F1.13_03
**User Story ID:** F1.13
**Test Case Title:** Verify user is logged in and navigated to Role Selection (F1.6) after successful LinkedIn Sign-Up
**Priority:** Medium
**Preconditions:**
    * User has successfully created an account via LinkedIn Sign-In (TC_F1.13_02).
**Test Steps:**
    1. Observe the screen presented immediately after successful LinkedIn Sign-In and account creation.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is automatically navigated to the "Select Current Role" screen (F1.6) as the first step of the onboarding process.
---
**Test Case ID:** TC_F1.13_04
**User Story ID:** F1.13
**Test Case Title:** Verify profile information (Name, Picture, Role if available) is pre-filled/suggested based on LinkedIn data
**Priority:** Low
**Preconditions:**
    * User created an account via LinkedIn Sign-In.
    * LinkedIn profile contained relevant data (Name, Picture, Headline/Role).
    * User is proceeding through onboarding (F1.6) or has completed it and is viewing profile (F1.8/F1.9).
**Test Steps:**
    1. During onboarding (F1.6), observe if the Current Role field is pre-filled or suggested based on LinkedIn Headline.
    2. After onboarding, navigate to the user's profile screen (F1.8).
    3. Observe the Full Name and Profile Picture.
**Test Data:**
    * LinkedIn profile data.
**Expected Results:**
    * The Full Name on the profile matches the name from the LinkedIn profile.
    * The Profile Picture matches the picture from the LinkedIn profile (if permission granted and picture exists).
    * The Current Role during onboarding (F1.6) may be pre-filled or suggested based on the LinkedIn Headline/Current Position, if available and mapped.
---
**Test Case ID:** TC_F1.14_01
**User Story ID:** F1.14
**Test Case Title:** Verify successful login using "Log In with Apple" for an existing account previously created/linked with Apple ID
**Priority:** Medium
**Preconditions:**
    * User previously created a Mockaccino account using "Sign Up with Apple" (F1.12).
    * User is logged out and on the login screen.
    * "Log In with Apple" button is visible.
**Test Steps:**
    1. Tap the "Log In with Apple" button.
    2. Complete the native Apple Sign-In authentication flow.
**Test Data:**
    * Apple ID credentials (same as used for sign-up).
**Expected Results:**
    * The user is authenticated using Apple Sign-In.
    * The system correctly identifies the existing Mockaccino account linked to that Apple ID.
    * The user is logged into their existing account and navigated to the main matching screen (F2.1).
---
**Test Case ID:** TC_F1.14_02
**User Story ID:** F1.14
**Test Case Title:** Verify successful login using "Log In with LinkedIn" for an existing account previously created/linked with LinkedIn
**Priority:** Medium
**Preconditions:**
    * User previously created a Mockaccino account using "Sign Up with LinkedIn" (F1.13).
    * User is logged out and on the login screen.
    * "Log In with LinkedIn" button is visible.
**Test Steps:**
    1. Tap the "Log In with LinkedIn" button.
    2. Complete the LinkedIn authentication and authorization flow.
**Test Data:**
    * LinkedIn credentials (same as used for sign-up).
**Expected Results:**
    * The user is authenticated using LinkedIn OAuth.
    * The system correctly identifies the existing Mockaccino account linked to that LinkedIn profile.
    * The user is logged into their existing account and navigated to the main matching screen (F2.1).
---
**Test Case ID:** TC_F1.14_03
**User Story ID:** F1.14
**Test Case Title:** Verify attempting "Log In with Apple" with an Apple ID not linked to any Mockaccino account shows an error or sign-up prompt
**Priority:** Low
**Preconditions:**
    * User is on the login screen.
    * The Apple ID being used for login attempt is *not* associated with any existing Mockaccino account.
**Test Steps:**
    1. Tap the "Log In with Apple" button.
    2. Complete the native Apple Sign-In authentication flow using the unlinked Apple ID.
**Test Data:**
    * Unlinked Apple ID credentials.
**Expected Results:**
    * Authentication with Apple succeeds.
    * The app displays a message indicating no account was found for this Apple ID.
    * The user might be prompted to sign up instead, or simply returned to the login screen with the error.
    * Login is unsuccessful.
---
**Test Case ID:** TC_F1.14_04
**User Story ID:** F1.14
**Test Case Title:** Verify attempting "Log In with LinkedIn" with a LinkedIn account not linked to any Mockaccino account shows an error or sign-up prompt
**Priority:** Low
**Preconditions:**
    * User is on the login screen.
    * The LinkedIn account being used for login attempt is *not* associated with any existing Mockaccino account.
**Test Steps:**
    1. Tap the "Log In with LinkedIn" button.
    2. Complete the LinkedIn authentication and authorization flow using the unlinked LinkedIn account.
**Test Data:**
    * Unlinked LinkedIn credentials.
**Expected Results:**
    * Authentication with LinkedIn succeeds.
    * The app displays a message indicating no account was found for this LinkedIn profile.
    * The user might be prompted to sign up instead, or simply returned to the login screen with the error.
    * Login is unsuccessful.
---
**Test Case ID:** TC_F2.1_01
**User Story ID:** F2.1
**Test Case Title:** Verify a profile card is displayed on the main screen after login and onboarding completion
**Priority:** High
**Preconditions:**
    * User is logged in.
    * User has completed the onboarding process (F1.6, F1.7).
    * There are potential matches available in the system meeting basic criteria.
**Test Steps:**
    1. Observe the main screen presented immediately after completing onboarding or subsequent logins.
**Test Data:**
    * N/A
**Expected Results:**
    * The main matching screen is displayed.
    * A profile card containing another user's information (Photo, Name, Role, etc. - see F2.3) is visible and presented to the user.
---
**Test Case ID:** TC_F2.1_02
**User Story ID:** F2.1
**Test Case Title:** Verify interacting with a card (swiping) loads the next potential match's card
**Priority:** High
**Preconditions:**
    * User is on the main matching screen (F2.1).
    * A profile card (User B) is currently displayed.
    * There is at least one more potential match (User C) available after User B.
**Test Steps:**
    1. Swipe the currently displayed card (User B) either left or right.
    2. Observe the screen after the swipe animation completes.
**Test Data:**
    * N/A
**Expected Results:**
    * The card for User B animates off the screen.
    * A new profile card for the next potential match (User C) is displayed.
---
**Test Case ID:** TC_F2.1_03
**User Story ID:** F2.1
**Test Case Title:** Verify a specific message is displayed when there are no more potential profiles to show
**Priority:** Medium
**Preconditions:**
    * User is logged in and on the main matching screen (F2.1).
    * The user has swiped through all available potential matches meeting the current criteria (including filters if applicable).
**Test Steps:**
    1. Continuously swipe left or right on profile cards until no more cards are presented.
    2. Observe the state of the main matching screen.
**Test Data:**
    * N/A
**Expected Results:**
    * After the last available profile card is swiped, no new card appears.
    * A message is displayed indicating that there are no more profiles (e.g., "No more profiles nearby", "You've seen everyone!", "Check back later").
---
**Test Case ID:** TC_F2.2_01
**User Story ID:** F2.2
**Test Case Title:** Verify swiping a profile card right registers a 'like' and displays the next card
**Priority:** High
**Preconditions:**
    * User is on the main matching screen (F2.1).
    * A profile card (User B) is displayed.
    * Another potential match (User C) exists.
**Test Steps:**
    1. Swipe the displayed card (User B) to the right.
**Test Data:**
    * N/A
**Expected Results:**
    * The swipe action is registered as a 'like' for User B (backend).
    * The card for User B animates off the screen.
    * The profile card for the next potential match (User C) is displayed (unless a mutual match occurred, see F2.4).
---
**Test Case ID:** TC_F2.2_02
**User Story ID:** F2.2
**Test Case Title:** Verify swiping a profile card left registers a 'pass' and displays the next card
**Priority:** High
**Preconditions:**
    * User is on the main matching screen (F2.1).
    * A profile card (User B) is displayed.
    * Another potential match (User C) exists.
**Test Steps:**
    1. Swipe the displayed card (User B) to the left.
**Test Data:**
    * N/A
**Expected Results:**
    * The swipe action is registered as a 'pass' for User B (backend).
    * The card for User B animates off the screen.
    * The profile card for the next potential match (User C) is displayed.
---
**Test Case ID:** TC_F2.2_03
**User Story ID:** F2.2
**Test Case Title:** Verify tapping the 'Heart' button registers a 'like' and displays the next card
**Priority:** High
**Preconditions:**
    * User is on the main matching screen (F2.1).
    * A profile card (User B) is displayed.
    * UI buttons for 'Like' (e.g., a Heart icon) and 'Pass' (e.g., an X icon) are visible below the card.
    * Another potential match (User C) exists.
**Test Steps:**
    1. Tap the 'Heart' button.
**Test Data:**
    * N/A
**Expected Results:**
    * The action is registered as a 'like' for User B (backend).
    * The card for User B animates off the screen or transitions away.
    * The profile card for the next potential match (User C) is displayed (unless a mutual match occurred, see F2.4).
---
**Test Case ID:** TC_F2.2_04
**User Story ID:** F2.2
**Test Case Title:** Verify tapping the 'X' button registers a 'pass' and displays the next card
**Priority:** High
**Preconditions:**
    * User is on the main matching screen (F2.1).
    * A profile card (User B) is displayed.
    * UI buttons for 'Like' (e.g., a Heart icon) and 'Pass' (e.g., an X icon) are visible below the card.
    * Another potential match (User C) exists.
**Test Steps:**
    1. Tap the 'X' button.
**Test Data:**
    * N/A
**Expected Results:**
    * The action is registered as a 'pass' for User B (backend).
    * The card for User B animates off the screen or transitions away.
    * The profile card for the next potential match (User C) is displayed.
---
**Test Case ID:** TC_F2.3_01
**User Story ID:** F2.3
**Test Case Title:** Verify profile card correctly displays the user's key information
**Priority:** High
**Preconditions:**
    * User is on the main matching screen (F2.1).
    * A profile card for User B is displayed.
    * User B has populated their profile with Photo, Name, City, Current Role, Target Role, Interaction Preference, and Bio.
**Test Steps:**
    1. Observe the content displayed on User B's profile card.
**Test Data:**
    * User B's Profile Data (as set up in their profile).
**Expected Results:**
    * User B's primary Profile Photo is displayed.
    * User B's Full Name is displayed.
    * User B's Location (City) is displayed.
    * User B's Current Role is displayed.
    * User B's Target Role is displayed.
    * User B's Interaction Preference (e.g., "Mock Interviews") is displayed.
    * A snippet (beginning portion) of User B's Bio is displayed.
---
**Test Case ID:** TC_F2.3_02
**User Story ID:** F2.3
**Test Case Title:** Verify profile card correctly displays Age if implemented and available
**Priority:** Low
**Preconditions:**
    * User is on the main matching screen (F2.1).
    * A profile card for User B is displayed.
    * The Age field has been implemented and User B's age is available and configured to be shown.
**Test Steps:**
    1. Observe the content displayed on User B's profile card, specifically looking for Age.
**Test Data:**
    * User B's Age (e.g., 30).
**Expected Results:**
    * User B's Age is displayed on the profile card.
---
**Test Case ID:** TC_F2.3_03
**User Story ID:** F2.3
**Test Case Title:** Verify profile card handles missing optional data gracefully (e.g., no Bio)
**Priority:** Medium
**Preconditions:**
    * User is on the main matching screen (F2.1).
    * A profile card for User B is displayed.
    * User B has *not* filled out their Bio. All other required card fields are present.
**Test Steps:**
    1. Observe the content displayed on User B's profile card, specifically the area where the Bio snippet would normally appear.
**Test Data:**
    * User B's Profile Data (with Bio field empty).
**Expected Results:**
    * The profile card displays all other required information (Photo, Name, City, Roles, Preference).
    * The Bio section is either completely absent or displays nothing, without causing layout issues or errors.
---
**Test Case ID:** TC_F2.4_01
**User Story ID:** F2.4
**Test Case Title:** Verify the "It's a Match!" screen appears immediately upon mutual like
**Priority:** High
**Preconditions:**
    * User A and User B are potential matches for each other.
    * User B has already swiped right ('liked') User A's profile.
    * User A is on the main matching screen (F2.1) and User B's profile card is currently displayed.
**Test Steps:**
    1. User A swipes right on User B's profile card.
    2. Observe the screen immediately following the swipe action.
**Test Data:**
    * User A swipes right on User B.
    * Pre-existing condition: User B swiped right on User A.
**Expected Results:**
    * Instead of the next profile card, an "It's a Match!" screen/overlay is displayed immediately to User A.
    * The screen indicates a mutual match has occurred.
---
**Test Case ID:** TC_F2.4_02
**User Story ID:** F2.4
**Test Case Title:** Verify the "It's a Match!" screen displays the matched user's picture and name
**Priority:** High
**Preconditions:**
    * A mutual match has just occurred, and the "It's a Match!" screen is displayed (TC_F2.4_01).
    * The match is between User A and User B.
**Test Steps:**
    1. Observe the content of the "It's a Match!" screen.
**Test Data:**
    * User B's profile picture.
    * User B's name.
**Expected Results:**
    * The "It's a Match!" screen prominently displays User B's profile picture.
    * The "It's a Match!" screen prominently displays User B's name.
---
**Test Case ID:** TC_F2.4_03
**User Story ID:** F2.4
**Test Case Title:** Verify the "It's a Match!" screen contains "Send a Message" and "Keep Swiping" options
**Priority:** High
**Preconditions:**
    * A mutual match has just occurred, and the "It's a Match!" screen is displayed (TC_F2.4_01).
**Test Steps:**
    1. Observe the buttons/options available on the "It's a Match!" screen.
**Test Data:**
    * N/A
**Expected Results:**
    * A button or option labeled "Send a Message" (or similar) is present.
    * A button or option labeled "Keep Swiping" (or similar) is present.
---
**Test Case ID:** TC_F2.4_04
**User Story ID:** F2.4
**Test Case Title:** Verify tapping "Keep Swiping" dismisses the match screen and returns to matching
**Priority:** High
**Preconditions:**
    * A mutual match has just occurred, and the "It's a Match!" screen is displayed (TC_F2.4_01).
    * The "Keep Swiping" option is visible.
**Test Steps:**
    1. Tap the "Keep Swiping" option.
**Test Data:**
    * N/A
**Expected Results:**
    * The "It's a Match!" screen is dismissed.
    * The user is returned to the main matching screen (F2.1), displaying the next available profile card (if any).
---
**Test Case ID:** TC_F2.4_05
**User Story ID:** F2.4
**Test Case Title:** Verify tapping "Send a Message" navigates to the chat screen with the matched user
**Priority:** High
**Preconditions:**
    * A mutual match has just occurred between User A and User B, and the "It's a Match!" screen is displayed to User A (TC_F2.4_01).
    * The "Send a Message" option is visible.
**Test Steps:**
    1. Tap the "Send a Message" option.
**Test Data:**
    * N/A
**Expected Results:**
    * The "It's a Match!" screen is dismissed.
    * The user (User A) is navigated to the individual chat screen (F3.4) for the conversation with User B.
---
**Test Case ID:** TC_F2.5_01
**User Story ID:** F2.5
**Test Case Title:** Verify free user is prevented from swiping right after reaching the daily limit
**Priority:** High
**Preconditions:**
    * User is logged in with a free tier account.
    * User is on the main matching screen (F2.1).
    * The user has already performed the maximum number of allowed right swipes for the current period.
    * A profile card is displayed.
**Test Steps:**
    1. Attempt to swipe right on the displayed profile card.
    2. OR, attempt to tap the 'Heart' button.
**Test Data:**
    * Free account that has reached swipe limit.
**Expected Results:**
    * The swipe right action is blocked or fails.
    * The profile card does not get 'liked'.
    * The 'Limit Reached' screen (F2.6) is displayed.
---
**Test Case ID:** TC_F2.5_02
**User Story ID:** F2.5
**Test Case Title:** Verify attempting to swipe right after reaching the limit triggers the 'Limit Reached' screen (F2.6)
**Priority:** High
**Preconditions:**
    * User is logged in with a free tier account.
    * User is on the main matching screen (F2.1).
    * The user has already performed the maximum number of allowed right swipes for the current period.
    * A profile card is displayed.
**Test Steps:**
    1. Attempt to swipe right on the displayed profile card OR tap the 'Heart' button.
    2. Observe the screen presented.
**Test Data:**
    * Free account that has reached swipe limit.
**Expected Results:**
    * The 'Likes Limit Reached' screen/overlay (described in F2.6) appears.
---
**Test Case ID:** TC_F2.5_03
**User Story ID:** F2.5
**Test Case Title:** Verify the right swipe allowance is reset after the defined period
**Priority:** Medium
**Preconditions:**
    * User is logged in with a free tier account.
    * User reached their right swipe limit in the previous period and saw the F2.6 screen.
    * The defined reset period (e.g., 24 hours) has passed since the limit was reached.
    * User is on the main matching screen (F2.1).
    * A profile card is displayed.
**Test Steps:**
    1. Attempt to swipe right on the displayed profile card OR tap the 'Heart' button.
**Test Data:**
    * Free account whose swipe limit reset time has passed.
**Expected Results:**
    * The swipe right action is successful (registered as a 'like').
    * The 'Limit Reached' screen (F2.6) is *not* displayed.
    * The next profile card is shown (unless a match occurred).
---
**Test Case ID:** TC_F2.5_04
**User Story ID:** F2.5
**Test Case Title:** Verify left swipes (pass) are not limited for free users
**Priority:** Medium
**Preconditions:**
    * User is logged in with a free tier account.
    * User is on the main matching screen (F2.1).
    * The user has already performed *more* left swipes than the daily *right* swipe limit.
    * A profile card is displayed.
**Test Steps:**
    1. Attempt to swipe left on the displayed profile card.
    2. OR, attempt to tap the 'X' button.
**Test Data:**
    * Free account.
**Expected Results:**
    * The swipe left action is successful (registered as a 'pass').
    * The 'Limit Reached' screen (F2.6) is *not* displayed.
    * The next profile card is shown.
---
**Test Case ID:** TC_F2.6_01
**User Story ID:** F2.6
**Test Case Title:** Verify the "Likes Limit Reached" screen appears when a free user attempts to swipe right after exhausting limit
**Priority:** High
**Preconditions:**
    * User is logged in with a free tier account.
    * User has used all their right swipes for the period (F2.5).
    * User is on the main matching screen (F2.1) with a profile card displayed.
**Test Steps:**
    1. Attempt to swipe right on the card OR tap the 'Heart' button.
**Test Data:**
    * N/A
**Expected Results:**
    * A screen or overlay specifically designed for the "Likes Limit Reached" scenario appears.
---
**Test Case ID:** TC_F2.6_02
**User Story ID:** F2.6
**Test Case Title:** Verify the "Likes Limit Reached" screen clearly indicates the limit has been reached
**Priority:** High
**Preconditions:**
    * The "Likes Limit Reached" screen is displayed (TC_F2.6_01).
**Test Steps:**
    1. Read the text content on the screen.
**Test Data:**
    * N/A
**Expected Results:**
    * The screen contains text clearly stating that the user has run out of likes for the current period (e.g., "You're out of likes!", "Daily Like Limit Reached").
---
**Test Case ID:** TC_F2.6_03
**User Story ID:** F2.6
**Test Case Title:** Verify the "Likes Limit Reached" screen displays the remaining time until reset
**Priority:** Medium
**Preconditions:**
    * The "Likes Limit Reached" screen is displayed (TC_F2.6_01).
**Test Steps:**
    1. Look for information regarding the reset time on the screen.
**Test Data:**
    * N/A
**Expected Results:**
    * The screen displays the time remaining until the user's like allowance will be reset (e.g., "Likes reset in 8h 15m", "Get more likes tomorrow").
---
**Test Case ID:** TC_F2.6_04
**User Story ID:** F2.6
**Test Case Title:** Verify the "Likes Limit Reached" screen contains an "Upgrade to Premium" button linking to F4.5
**Priority:** High
**Preconditions:**
    * The "Likes Limit Reached" screen is displayed (TC_F2.6_01).
**Test Steps:**
    1. Look for a button or link related to upgrading.
    2. Tap the "Upgrade to Premium" (or similar) button/link.
**Test Data:**
    * N/A
**Expected Results:**
    * A prominent button/link labeled "Upgrade to Premium", "Get Unlimited Likes", or similar is present.
    * Tapping this button navigates the user to the Premium subscription screen (F4.5).
---
**Test Case ID:** TC_F2.6_05
**User Story ID:** F2.6
**Test Case Title:** Verify dismissing the limit screen returns user to matching, but right swipes remain disabled
**Priority:** Medium
**Preconditions:**
    * The "Likes Limit Reached" screen is displayed (TC_F2.6_01).
    * The screen has a dismiss option (e.g., a close button 'X', or tapping outside the overlay).
**Test Steps:**
    1. Dismiss the "Likes Limit Reached" screen using the available mechanism.
    2. Observe the main matching screen.
    3. Attempt to swipe right on the profile card again OR tap the 'Heart' button.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is returned to the main matching screen, showing the same profile card they were viewing.
    * Attempting to swipe right or tap 'Heart' still fails and likely brings up the "Likes Limit Reached" screen again.
---
**Test Case ID:** TC_F3.1_01
**User Story ID:** F3.1
**Test Case Title:** Verify a "Chats" tab/navigation item is present in the main app interface
**Priority:** High
**Preconditions:**
    * User is logged in.
    * User is viewing the main app interface (e.g., the matching screen F2.1, or profile screen F1.8).
**Test Steps:**
    1. Observe the main navigation elements (e.g., bottom tab bar, side menu).
**Test Data:**
    * N/A
**Expected Results:**
    * A distinct tab or navigation item labeled "Chats" or similar (e.g., a speech bubble icon) is visible and accessible.
---
**Test Case ID:** TC_F3.1_02
**User Story ID:** F3.1
**Test Case Title:** Verify navigating to the "Chats" tab displays a list of matched users
**Priority:** High
**Preconditions:**
    * User is logged in.
    * User has one or more matches (F2.4) (e.g., matched with User B and User C).
**Test Steps:**
    1. Tap the "Chats" tab/navigation item.
    2. Observe the content of the Chats screen.
**Test Data:**
    * Existing matches: User B, User C.
**Expected Results:**
    * The user is navigated to the Chats screen.
    * A list is displayed containing entries for each match (User B, User C). Each entry represents a potential or ongoing conversation.
---
**Test Case ID:** TC_F3.1_03
**User Story ID:** F3.1
**Test Case Title:** Verify an empty state message is displayed on the "Chats" tab when the user has no matches
**Priority:** Medium
**Preconditions:**
    * User is logged in.
    * User has *no* matches.
**Test Steps:**
    1. Tap the "Chats" tab/navigation item.
    2. Observe the content of the Chats screen.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is navigated to the Chats screen.
    * Instead of a list of conversations, an empty state message is displayed (e.g., "Your matches will appear here", "Start swiping to find matches!").
---
**Test Case ID:** TC_F3.2_01
**User Story ID:** F3.2
**Test Case Title:** Verify each chat list row displays the match's profile picture and name
**Priority:** High
**Preconditions:**
    * User is on the "Chats" tab (F3.1).
    * The list displays at least one conversation row for a match (e.g., User B).
    * User B has a profile picture and name.
**Test Steps:**
    1. Observe a specific conversation row in the list (for User B).
**Test Data:**
    * User B's name and profile picture.
**Expected Results:**
    * The row clearly displays User B's profile picture.
    * The row clearly displays User B's name.
---
**Test Case ID:** TC_F3.2_02
**User Story ID:** F3.2
**Test Case Title:** Verify chat list row displays preview of the last exchanged message
**Priority:** High
**Preconditions:**
    * User is on the "Chats" tab (F3.1).
    * A conversation row for User B is displayed.
    * At least one message has been exchanged between the user and User B. The last message was "Hello there!".
**Test Steps:**
    1. Observe the conversation row for User B, below the name.
**Test Data:**
    * Last message: "Hello there!"
**Expected Results:**
    * A text preview of the last message ("Hello there!") is displayed in the row. The preview might be truncated if the message is long.
---
**Test Case ID:** TC_F3.2_03
**User Story ID:** F3.2
**Test Case Title:** Verify chat list row displays timestamp of the last message
**Priority:** High
**Preconditions:**
    * User is on the "Chats" tab (F3.1).
    * A conversation row for User B is displayed.
    * The last message in the conversation was sent/received at a specific time (e.g., 10:30 AM today).
**Test Steps:**
    1. Observe the conversation row for User B, typically near the name or message preview.
**Test Data:**
    * Timestamp of last message: Today, 10:30 AM.
**Expected Results:**
    * The timestamp of the last message is displayed in a user-friendly format (e.g., "10:30 AM", "Yesterday", "Apr 10").
---
**Test Case ID:** TC_F3.2_04
**User Story ID:** F3.2
**Test Case Title:** Verify unread indicator is displayed on chat list rows with unread messages
**Priority:** High
**Preconditions:**
    * User is on the "Chats" tab (F3.1).
    * User B sent a new message to the user.
    * The user has *not* yet opened the chat screen with User B since the message arrived.
**Test Steps:**
    1. Observe the conversation row for User B in the chat list.
**Test Data:**
    * 1 unread message from User B.
**Expected Results:**
    * A visual indicator is present on User B's conversation row signifying unread messages (e.g., a colored dot, a badge with count '1', bold text for name/message preview).
---
**Test Case ID:** TC_F3.2_05
**User Story ID:** F3.2
**Test Case Title:** Verify no unread indicator is displayed on chat list rows where all messages have been read
**Priority:** High
**Preconditions:**
    * User is on the "Chats" tab (F3.1).
    * A conversation row for User B is displayed.
    * The user has opened and viewed all messages in the conversation with User B.
**Test Steps:**
    1. Observe the conversation row for User B in the chat list.
**Test Data:**
    * 0 unread messages from User B.
**Expected Results:**
    * There is no unread indicator (dot, badge, bold text) visible on User B's conversation row.
---
**Test Case ID:** TC_F3.3_01
**User Story ID:** F3.3
**Test Case Title:** Verify tapping a conversation row navigates to the individual chat screen
**Priority:** High
**Preconditions:**
    * User is on the "Chats" tab (F3.1) viewing the conversation list.
    * A conversation row for a match (User B) is visible.
**Test Steps:**
    1. Tap on the conversation row corresponding to User B.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is navigated away from the chat list screen.
    * The individual chat screen (F3.4) for the conversation with User B is displayed.
    * The header of the chat screen likely shows User B's name and picture.
---
**Test Case ID:** TC_F3.4_01
**User Story ID:** F3.4
**Test Case Title:** Verify the chat screen displays message history in chronological order
**Priority:** High
**Preconditions:**
    * User has opened the chat screen with User B (TC_F3.3_01).
    * A history of messages exists between the user and User B (e.g., Msg1: User A, Msg2: User B, Msg3: User A).
**Test Steps:**
    1. Observe the arrangement of messages displayed in the chat view.
**Test Data:**
    * Message History:
        * 10:00 AM User A: Hi!
        * 10:01 AM User B: Hello! How are you?
        * 10:02 AM User A: Good, thanks!
**Expected Results:**
    * Messages are displayed in order from oldest to newest (or newest to oldest, consistently). Assuming oldest at top: "Hi!" appears first, then "Hello! How are you?", then "Good, thanks!".
---
**Test Case ID:** TC_F3.4_02
**User Story ID:** F3.4
**Test Case Title:** Verify own messages and the match's messages are visually distinct
**Priority:** High
**Preconditions:**
    * User is on the chat screen with User B.
    * Messages from both the user (User A) and the match (User B) are displayed.
**Test Steps:**
    1. Observe the appearance of messages sent by User A.
    2. Observe the appearance of messages sent by User B.
**Test Data:**
    * N/A
**Expected Results:**
    * Messages sent by User A have a distinct visual style compared to messages sent by User B (e.g., different background color, different alignment - User A right-aligned, User B left-aligned).
---
**Test Case ID:** TC_F3.4_03
**User Story ID:** F3.4
**Test Case Title:** Verify message text and timestamps are correctly displayed
**Priority:** High
**Preconditions:**
    * User is on the chat screen with User B.
    * Messages with specific text and timestamps are displayed.
**Test Steps:**
    1. Observe individual message bubbles.
**Test Data:**
    * Message: "Let's connect soon." sent at 11:15 AM.
**Expected Results:**
    * The message bubble correctly displays the text "Let's connect soon.".
    * A timestamp (e.g., "11:15 AM") is displayed associated with the message (either within/near the bubble or grouped with nearby messages).
---
**Test Case ID:** TC_F3.4_04
**User Story ID:** F3.4
**Test Case Title:** Verify text input field and "Send" button are visible and functional
**Priority:** High
**Preconditions:**
    * User is on the chat screen with User B.
**Test Steps:**
    1. Observe the bottom area of the chat screen.
    2. Tap into the text input field.
    3. Type some text.
**Test Data:**
    * Text: Test message
**Expected Results:**
    * A text input field is visible, allowing the user to type.
    * A "Send" button (or icon, e.g., paper airplane) is visible, likely near the input field.
    * Typing text into the field works as expected. The "Send" button may become enabled only when text is present.
---
**Test Case ID:** TC_F3.4_05
**User Story ID:** F3.4
**Test Case Title:** Verify sending a message clears input, displays locally, and sends to recipient
**Priority:** High
**Preconditions:**
    * User (User A) is on the chat screen with User B.
    * Text input field and Send button are visible.
    * (Requires ability to monitor User B's perspective or backend confirmation).
**Test Steps:**
    1. Type a message into the text input field.
    2. Tap the "Send" button.
    3. Observe the text input field immediately after tapping Send.
    4. Observe the chat history area.
    5. (Verification) Check User B's chat screen with User A.
**Test Data:**
    * Message Text: "Sending this message now."
**Expected Results:**
    * The text input field is cleared.
    * The sent message ("Sending this message now.") appears instantly in User A's chat history, styled as an outgoing message.
    * The message is successfully delivered to User B (appears on User B's chat screen).
---
**Test Case ID:** TC_F3.4_06
**User Story ID:** F3.4
**Test Case Title:** Verify receiving a message displays it correctly in the chat history
**Priority:** High
**Preconditions:**
    * User (User A) is on the chat screen with User B.
    * User B sends a message to User A.
    * Real-time connection is active.
**Test Steps:**
    1. Have User B send a message to User A.
    2. Observe User A's chat screen.
**Test Data:**
    * Message sent by User B: "Received!"
**Expected Results:**
    * The new message ("Received!") appears in User A's chat history almost instantly.
    * The message is styled as an incoming message (visually distinct from User A's messages).
    * The chat view may scroll automatically to show the new message.
---
**Test Case ID:** TC_F3.5_01
**User Story ID:** F3.5
**Test Case Title:** Verify push notification is received when a message arrives while app is backgrounded/closed
**Priority:** Medium
**Preconditions:**
    * User A is logged in.
    * User A has granted push notification permissions to the app.
    * User A has matched with User B.
    * User A's Mockaccino app is currently backgrounded or closed.
    * User B sends a message to User A.
**Test Steps:**
    1. Have User B send a message to User A.
    2. Observe User A's device notifications outside the Mockaccino app.
**Test Data:**
    * Message sent by User B: "Push notification test"
**Expected Results:**
    * A push notification appears on User A's device.
    * The notification indicates a new message has been received from Mockaccino.
---
**Test Case ID:** TC_F3.5_02
**User Story ID:** F3.5
**Test Case Title:** Verify push notification content includes sender name and message snippet
**Priority:** Medium
**Preconditions:**
    * A push notification for a new message has been received (TC_F3.5_01).
    * The message was sent by User B.
**Test Steps:**
    1. Examine the content of the received push notification on User A's device (e.g., in the notification center).
**Test Data:**
    * Sender: User B Name
    * Message: "Push notification test"
**Expected Results:**
    * The push notification displays the sender's name (User B Name).
    * The push notification displays at least a snippet of the message content ("Push notification test").
---
**Test Case ID:** TC_F3.5_03
**User Story ID:** F3.5
**Test Case Title:** Verify in-app notification/indicator updates when message arrives while app open but chat not focused
**Priority:** Medium
**Preconditions:**
    * User A is logged into the app and the app is open and active.
    * User A is *not* currently viewing the chat screen with User B (e.g., User A is on the matching screen F2.1 or Chats list F3.1).
    * User B sends a message to User A.
**Test Steps:**
    1. Have User B send a message to User A.
    2. Observe User A's app interface (e.g., top banner area, Chats tab indicator).
**Test Data:**
    * Message sent by User B: "In-app notification test"
**Expected Results:**
    * An in-app notification might appear briefly (e.g., a banner at the top showing sender and message snippet).
    * AND/OR The unread indicator on the main "Chats" tab (F3.1) updates to show a new unread message.
    * AND/OR The specific conversation row for User B in the Chats list (F3.2) updates with an unread indicator.
---
**Test Case ID:** TC_F3.5_04
**User Story ID:** F3.5
**Test Case Title:** Verify tapping a push notification opens the app directly to the corresponding chat screen
**Priority:** Medium
**Preconditions:**
    * User A has received a push notification for a new message from User B (TC_F3.5_01).
    * The Mockaccino app may be closed or backgrounded.
**Test Steps:**
    1. Tap on the push notification for the message from User B.
**Test Data:**
    * N/A
**Expected Results:**
    * The Mockaccino app opens or is brought to the foreground.
    * The app navigates directly to the individual chat screen (F3.4) for the conversation with User B.
---
**Test Case ID:** TC_F3.5_05
**User Story ID:** F3.5
**Test Case Title:** Verify no separate notification is received if message arrives while chat screen is active
**Priority:** Medium
**Preconditions:**
    * User A is logged in and actively viewing the chat screen (F3.4) with User B.
    * User B sends a message to User A.
**Test Steps:**
    1. Have User B send a message to User A.
    2. Observe User A's screen for any separate notification banners (push or in-app).
    3. Observe the chat history.
**Test Data:**
    * Message sent by User B: "Chat already open"
**Expected Results:**
    * No separate push notification is received.
    * No separate in-app notification banner appears.
    * The new message ("Chat already open") simply appears directly in the chat history (as per TC_F3.4_06).
---
**Test Case ID:** TC_F4.1_01
**User Story ID:** F4.1
**Test Case Title:** Verify Premium user can perform more right swipes than the free daily limit
**Priority:** High
**Preconditions:**
    * User is logged in with an active Premium subscription (F4.6).
    * User is on the main matching screen (F2.1).
    * There are enough available profiles to exceed the standard free daily like limit (e.g., > 50 if limit is 50).
    * Define free daily limit (e.g., `FREE_LIMIT`).
**Test Steps:**
    1. Continuously swipe right on profile cards.
    2. Keep track of the number of right swipes performed.
    3. Continue swiping right past the `FREE_LIMIT` number.
**Test Data:**
    * Premium account.
    * Number of right swipes > `FREE_LIMIT`.
**Expected Results:**
    * The user can successfully perform more than `FREE_LIMIT` right swipes.
    * Each right swipe registers successfully (loads next card or shows match screen).
    * The "Likes Limit Reached" screen (F2.6) is not displayed.
---
**Test Case ID:** TC_F4.1_02
**User Story ID:** F4.1
**Test Case Title:** Verify the "Likes Limit Reached" screen is never displayed to a Premium user
**Priority:** High
**Preconditions:**
    * User is logged in with an active Premium subscription.
    * User is on the main matching screen (F2.1).
**Test Steps:**
    1. Perform a large number of right swipes (e.g., 100+ or until profiles run out).
    2. Observe if the "Likes Limit Reached" screen (F2.6) ever appears.
**Test Data:**
    * Premium account.
**Expected Results:**
    * The "Likes Limit Reached" screen (F2.6) is never displayed, regardless of the number of right swipes performed.
---
**Test Case ID:** TC_F4.1_03
**User Story ID:** F4.1
**Test Case Title:** Verify swipe limits are re-enforced if Premium subscription expires
**Priority:** Medium
**Preconditions:**
    * User had an active Premium subscription, which has now expired.
    * User is logged in (account reverts to free tier).
    * User is on the main matching screen (F2.1).
    * User performs right swipes up to the free daily limit (`FREE_LIMIT`).
**Test Steps:**
    1. Perform `FREE_LIMIT` right swipes successfully.
    2. Attempt to perform one more right swipe (`FREE_LIMIT` + 1).
**Test Data:**
    * Expired Premium account (now free tier).
**Expected Results:**
    * The first `FREE_LIMIT` right swipes are successful.
    * The attempt to perform the (`FREE_LIMIT` + 1)-th right swipe fails.
    * The "Likes Limit Reached" screen (F2.6) is displayed.
---
**Test Case ID:** TC_F4.2_01
**User Story ID:** F4.2
**Test Case Title:** Verify "Likes" tab is visible and accessible only to Premium users
**Priority:** High
**Preconditions:**
    * Test with two users: User A (Premium), User B (Free).
    * Both users are logged in.
**Test Steps:**
    1. Observe the main navigation interface for User A (Premium).
    2. Attempt to navigate to the "Likes" tab as User A.
    3. Observe the main navigation interface for User B (Free).
    4. Attempt to navigate to the "Likes" tab as User B (if visible).
**Test Data:**
    * User A: Premium account
    * User B: Free account
**Expected Results:**
    * For User A (Premium): A "Likes" tab/icon is visible in the main navigation. Tapping it successfully navigates to the "Likes You" screen (F4.2).
    * For User B (Free): The "Likes" tab is either not visible, or if visible, tapping it redirects to the Premium upsell screen (F4.5) instead of the actual feature.
---
**Test Case ID:** TC_F4.2_02
**User Story ID:** F4.2
**Test Case Title:** Verify "Likes" tab displays users who have liked the Premium user
**Priority:** High
**Preconditions:**
    * User A is logged in with a Premium subscription.
    * Several other users (User B, User C) have previously swiped right ('liked') on User A.
    * User A has *not* yet swiped left or right on User B or User C.
**Test Steps:**
    1. User A navigates to the "Likes" tab.
    2. Observe the list/grid of users displayed.
**Test Data:**
    * Likers: User B, User C.
**Expected Results:**
    * The "Likes" screen displays profile summaries (picture, name, etc.) for User B and User C.
    * Users whom User A has already swiped on (left or right) should not appear in this list.
---
**Test Case ID:** TC_F4.2_03
**User Story ID:** F4.2
**Test Case Title:** Verify tapping a user card in the "Likes" list allows interaction
**Priority:** Medium
**Preconditions:**
    * User A (Premium) is on the "Likes" tab viewing the list of likers (TC_F4.2_02).
    * A card for User B is displayed in the list.
**Test Steps:**
    1. Tap on the profile card/summary for User B within the "Likes" list.
**Test Data:**
    * N/A
**Expected Results:**
    * EITHER: The user is navigated to User B's full profile view (similar to F1.8).
    * OR: Interaction elements (like/pass buttons, or swipe capability) become active directly on the card within the Likes screen, allowing User A to swipe right/left on User B. (Behavior depends on specific design).
---
**Test Case ID:** TC_F4.2_04
**User Story ID:** F4.2
**Test Case Title:** Verify swiping right from "Likes" tab results in immediate match and removal from list
**Priority:** High
**Preconditions:**
    * User A (Premium) is on the "Likes" tab viewing the list of likers.
    * A card for User B is displayed in the list.
    * Interaction (swipe/button) is enabled on the list item.
**Test Steps:**
    1. Swipe right (or tap 'Like' button) on User B's card within the "Likes" list.
    2. Observe the immediate result (match notification).
    3. Observe the "Likes" list after the action.
**Test Data:**
    * N/A
**Expected Results:**
    * An "It's a Match!" screen (F2.4) is displayed immediately for User A and User B.
    * User B is removed from User A's "Likes" list.
---
**Test Case ID:** TC_F4.2_05
**User Story ID:** F4.2
**Test Case Title:** Verify swiping left from "Likes" tab removes user from list without match
**Priority:** High
**Preconditions:**
    * User A (Premium) is on the "Likes" tab viewing the list of likers.
    * A card for User B is displayed in the list.
    * Interaction (swipe/button) is enabled on the list item.
**Test Steps:**
    1. Swipe left (or tap 'Pass' button) on User B's card within the "Likes" list.
    2. Observe the "Likes" list after the action.
    3. Check if a match was created (e.g., check Chats list F3.1).
**Test Data:**
    * N/A
**Expected Results:**
    * User B is removed from User A's "Likes" list.
    * No "It's a Match!" screen appears.
    * No new conversation with User B appears in the Chats list (F3.1).
---
**Test Case ID:** TC_F4.2_06
**User Story ID:** F4.2
**Test Case Title:** Verify "Likes" list shows empty state if no users have liked the Premium user
**Priority:** Medium
**Preconditions:**
    * User A is logged in with a Premium subscription.
    * *No* other users have swiped right on User A yet, OR all users who liked User A have already been swiped on by User A.
**Test Steps:**
    1. User A navigates to the "Likes" tab.
    2. Observe the content of the screen.
**Test Data:**
    * N/A
**Expected Results:**
    * The "Likes" screen displays an empty state message (e.g., "People who like you will appear here", "No likes yet").
    * No user profile cards are displayed.
---
**Test Case ID:** TC_F4.3_01
**User Story ID:** F4.3
**Test Case Title:** Verify filter options are accessible only to Premium users
**Priority:** High
**Preconditions:**
    * Test with two users: User A (Premium), User B (Free).
    * Both users are logged in and on the main matching screen (F2.1).
    * A button/icon to access filters is present on the matching screen.
**Test Steps:**
    1. User A (Premium) taps the filter access button/icon.
    2. User B (Free) taps the filter access button/icon.
**Test Data:**
    * User A: Premium account
    * User B: Free account
**Expected Results:**
    * For User A (Premium): The filters screen/panel opens, displaying options for Role, Preference, Distance, City.
    * For User B (Free): Tapping the filter button either does nothing, is disabled, or navigates to the Premium upsell screen (F4.5). User B cannot access the actual filter controls.
---
**Test Case ID:** TC_F4.3_02
**User Story ID:** F4.3
**Test Case Title:** Verify Premium user can select and apply multiple filters
**Priority:** High
**Preconditions:**
    * User A (Premium) is accessing the filter options (TC_F4.3_01).
**Test Steps:**
    1. Select a specific Current Role filter (e.g., "Software Engineer").
    2. Select a specific Interaction Preference filter (e.g., "Mock Interviews").
    3. Adjust the Search Distance filter (e.g., to 50 km).
    4. Enter a specific City filter (e.g., "Calgary").
    5. Tap "Apply" or "Done" to confirm the filters.
**Test Data:**
    * Filters:
        * Current Role: Software Engineer
        * Preference: Mock Interviews
        * Distance: 50 km
        * City: Calgary
**Expected Results:**
    * The filter selections are registered in the UI.
    * Applying the filters closes the filter screen/panel.
    * The main matching screen (F2.1) is now expected to show only profiles matching *all* applied criteria.
---
**Test Case ID:** TC_F4.3_03
**User Story ID:** F4.3
**Test Case Title:** Verify applying filters results in matching queue showing only matching profiles
**Priority:** High
**Preconditions:**
    * User A (Premium) has applied specific filters (e.g., from TC_F4.3_02: Current Role='SE', Pref='Mock', Dist=50km, City='Calgary').
    * User A is viewing the main matching screen (F2.1).
    * There are profiles available that match the criteria (e.g., User B is an SE in Calgary wanting Mock Interviews within 50km).
    * There are profiles available that *do not* match the criteria (e.g., User C is a PM in Edmonton wanting Referrals).
**Test Steps:**
    1. Observe the first profile card displayed after applying filters.
    2. Swipe through several profile cards presented.
    3. Verify the details on the displayed cards against the applied filters.
**Test Data:**
    * Applied Filters: Current Role='SE', Pref='Mock', Dist=50km, City='Calgary'
    * Available Profiles: User B (matches), User C (does not match)
**Expected Results:**
    * The first profile card shown (and subsequent cards) belong to users who meet *all* the applied filter criteria (e.g., User B is shown).
    * Profiles that do not meet the criteria (e.g., User C) are *not* shown in the matching queue while the filters are active.
---
**Test Case ID:** TC_F4.3_04
**User Story ID:** F4.3
**Test Case Title:** Verify a visual indicator is displayed when filters are active
**Priority:** Medium
**Preconditions:**
    * User A (Premium) has applied one or more filters (TC_F4.3_02).
    * User A is viewing the main matching screen (F2.1).
**Test Steps:**
    1. Observe the main matching screen, particularly near the filter access button or top of the screen.
**Test Data:**
    * N/A
**Expected Results:**
    * A visual indicator (e.g., a highlighted filter icon, a badge, text like "Filters Active") is displayed, informing the user that the matching queue is currently filtered.
---
**Test Case ID:** TC_F4.3_05
**User Story ID:** F4.3
**Test Case Title:** Verify clearing filters removes constraints and updates the matching queue
**Priority:** High
**Preconditions:**
    * User A (Premium) has applied specific filters (TC_F4.3_02).
    * A visual indicator shows filters are active (TC_F4.3_04).
    * Profiles exist that were previously excluded by the filters (e.g., User C from TC_F4.3_03).
**Test Steps:**
    1. Access the filter options again.
    2. Select an option to "Clear Filters" or "Reset".
    3. Apply the cleared filters (e.g., tap "Done").
    4. Observe the visual indicator for active filters on the matching screen.
    5. Observe the profiles presented in the matching queue.
**Test Data:**
    * N/A
**Expected Results:**
    * All filter selections are cleared in the filter UI.
    * The visual indicator for active filters on the matching screen disappears.
    * The matching queue is updated to include profiles that were previously excluded by the filters (e.g., User C might now appear).
---
**Test Case ID:** TC_F4.4_01
**User Story ID:** F4.4
**Test Case Title:** Verify free user tapping "Likes" tab is shown Premium promotion screen
**Priority:** Medium
**Preconditions:**
    * User is logged in with a free tier account.
    * The "Likes" tab/icon (F4.2) is visible in the navigation (even if non-functional for free users).
**Test Steps:**
    1. Tap the "Likes" tab/icon.
**Test Data:**
    * Free account.
**Expected Results:**
    * The user is *not* shown the list of users who liked them.
    * Instead, the user is navigated to the Premium subscription promotion screen (F4.5).
---
**Test Case ID:** TC_F4.4_02
**User Story ID:** F4.4
**Test Case Title:** Verify free user attempting to access advanced filters is shown Premium promotion screen
**Priority:** Medium
**Preconditions:**
    * User is logged in with a free tier account.
    * User is on the main matching screen (F2.1).
    * A button/icon to access filters (F4.3) is visible.
**Test Steps:**
    1. Tap the filter access button/icon.
**Test Data:**
    * Free account.
**Expected Results:**
    * The user is *not* shown the filter selection controls.
    * Instead, the user is navigated to the Premium subscription promotion screen (F4.5).
---
**Test Case ID:** TC_F4.5_01
**User Story ID:** F4.5
**Test Case Title:** Verify Premium subscription screen clearly lists the key benefits
**Priority:** High
**Preconditions:**
    * User navigates to the Premium subscription screen (e.g., via prompts F4.4, F2.6, or a Settings link).
**Test Steps:**
    1. Observe the content displayed on the Premium subscription screen. Look for the list of benefits.
**Test Data:**
    * N/A
**Expected Results:**
    * The screen clearly lists the main benefits of Premium, including:
        * "Unlimited Right Swipes" (or similar wording for F4.1 benefit)
        * "See Who Likes You" (or similar wording for F4.2 benefit)
        * "Advanced Filters" (or similar wording for F4.3 benefit)
---
**Test Case ID:** TC_F4.5_02
**User Story ID:** F4.5
**Test Case Title:** Verify Premium subscription screen clearly displays the subscription price
**Priority:** High
**Preconditions:**
    * User is viewing the Premium subscription screen (F4.5).
**Test Steps:**
    1. Observe the content displayed on the screen. Look for the price information.
**Test Data:**
    * Expected Price: $3.99/month (as per user story)
**Expected Results:**
    * The screen clearly states the subscription price and billing frequency (e.g., "$3.99 / month").
---
**Test Case ID:** TC_F4.5_03
**User Story ID:** F4.5
**Test Case Title:** Verify Premium subscription screen contains a clear call-to-action button to purchase
**Priority:** High
**Preconditions:**
    * User is viewing the Premium subscription screen (F4.5).
    * User does not currently have an active Premium subscription.
**Test Steps:**
    1. Observe the buttons available on the screen.
**Test Data:**
    * N/A
**Expected Results:**
    * A prominent button with a clear call-to-action is present, intended to initiate the purchase process (e.g., "Get Premium", "Subscribe Now", "Start Free Trial" if applicable).
---
**Test Case ID:** TC_F4.5_04
**User Story ID:** F4.5
**Test Case Title:** Verify links to subscription/payment terms are present if applicable
**Priority:** Low
**Preconditions:**
    * User is viewing the Premium subscription screen (F4.5).
**Test Steps:**
    1. Scan the screen for links related to terms and conditions or payment policies.
**Test Data:**
    * N/A
**Expected Results:**
    * If required by platform guidelines or company policy, links to relevant terms (e.g., "Subscription Terms", "Payment Policy") are visible, often near the purchase button or as fine print.
---
**Test Case ID:** TC_F4.6_01
**User Story ID:** F4.6
**Test Case Title:** Verify tapping subscribe button initiates native platform In-App Purchase flow
**Priority:** High
**Preconditions:**
    * User is on the Premium subscription screen (F4.5).
    * User does not have an active Premium subscription.
    * The "Get Premium" / "Subscribe" button is visible.
    * User is on a device capable of In-App Purchases (iOS or Android) and is logged into their respective store account (App Store / Google Play).
**Test Steps:**
    1. Tap the "Get Premium" / "Subscribe" button.
**Test Data:**
    * N/A
**Expected Results:**
    * The Mockaccino app initiates the standard In-App Purchase flow provided by the operating system (iOS App Store or Google Play Store).
    * A native system dialog appears, showing the subscription details (name, price, duration, renewal info) and prompting the user to confirm the purchase (e.g., using Face ID, Touch ID, password, or Play Store confirmation).
---
**Test Case ID:** TC_F4.6_02
**User Story ID:** F4.6
**Test Case Title:** Verify successfully completing platform IAP flow updates Mockaccino account to Premium
**Priority:** High
**Preconditions:**
    * User has initiated the IAP flow (TC_F4.6_01).
    * User successfully confirms and completes the purchase through the native platform dialog.
    * Backend receipt validation is functional.
**Test Steps:**
    1. Confirm the purchase in the native platform dialog.
    2. Wait for the purchase confirmation within the Mockaccino app.
    3. Check the user's subscription status (e.g., by revisiting the Premium screen F4.5 or checking profile indicators if any).
**Test Data:**
    * Valid payment method linked to App Store / Google Play account.
**Expected Results:**
    * The platform confirms the purchase was successful.
    * The Mockaccino app receives confirmation (after backend validation).
    * The user's account status within Mockaccino is updated to 'Premium'.
    * A success message might be displayed in the app.
---
**Test Case ID:** TC_F4.6_03
**User Story ID:** F4.6
**Test Case Title:** Verify Premium features are immediately available after successful purchase
**Priority:** High
**Preconditions:**
    * User has just successfully purchased Premium (TC_F4.6_02).
    * User's account status is updated to Premium.
**Test Steps:**
    1. Attempt to perform more right swipes than the free limit (verify F4.1).
    2. Navigate to check if the "Likes" tab is now accessible and functional (verify F4.2).
    3. Navigate to the matching screen and attempt to access filters (verify F4.3).
**Test Data:**
    * N/A
**Expected Results:**
    * User can perform unlimited right swipes without hitting the limit screen.
    * User can access the "Likes" tab and see users who liked them (if any).
    * User can access and apply advanced filters.
    * Premium features are unlocked without needing to restart the app.
---
**Test Case ID:** TC_F4.6_04
**User Story ID:** F4.6
**Test Case Title:** Verify cancelling or failing IAP flow does not change account status
**Priority:** Medium
**Preconditions:**
    * User has initiated the IAP flow (TC_F4.6_01).
    * User is presented with the native platform confirmation dialog.
**Test Steps:**
    1. Cancel the purchase from the native platform dialog.
    2. OR, trigger a payment failure (e.g., invalid payment method if testable).
    3. Return to the Mockaccino app.
    4. Check the user's subscription status (e.g., revisit Premium screen F4.5).
    5. Attempt to access a Premium feature (e.g., Filters F4.3).
**Test Data:**
    * N/A
**Expected Results:**
    * The user is returned to the Mockaccino app, likely back on the Premium screen (F4.5).
    * An appropriate message indicating cancellation or failure might be shown.
    * The user's account status remains 'Free'.
    * Accessing Premium features still results in the upsell prompt (F4.4).
---
**Test Case ID:** TC_F4.6_05
**User Story ID:** F4.6
**Test Case Title:** Verify revisiting Premium screen shows active status/manage options for subscribed user
**Priority:** Medium
**Preconditions:**
    * User has an active Premium subscription (purchased via TC_F4.6_02).
    * User navigates away from the Premium screen and then returns to it later.
**Test Steps:**
    1. Navigate to the Premium subscription screen (F4.5) again (e.g., via Settings).
**Test Data:**
    * N/A
**Expected Results:**
    * The screen no longer shows the "Get Premium" button as the primary action.
    * Instead, it indicates that the user currently has an active Premium subscription.
    * It may display the subscription expiry date or next renewal date.
    * It may provide options to manage the subscription (which typically link out to the platform's subscription management settings - App Store / Google Play).
---
**Test Case ID:** TC_F5.1_01
**User Story ID:** F5.1
**Test Case Title:** Verify a "Settings" or "Account" section is accessible from main app navigation
**Priority:** High
**Preconditions:**
    * User is logged in.
**Test Steps:**
    1. Explore the main navigation elements of the app (e.g., bottom tab bar, side menu, profile screen).
    2. Locate and tap the entry point for "Settings" or "Account".
**Test Data:**
    * N/A
**Expected Results:**
    * A clear entry point (e.g., "Settings" tab, gear icon on profile) exists.
    * Tapping the entry point navigates the user to the main Settings screen.
---
**Test Case ID:** TC_F5.1_02
**User Story ID:** F5.1
**Test Case Title:** Verify Settings screen contains options/links for account management
**Priority:** High
**Preconditions:**
    * User is on the main Settings screen (TC_F5.1_01).
**Test Steps:**
    1. Observe the sections and options listed on the Settings screen.
**Test Data:**
    * N/A
**Expected Results:**
    * Options related to account management are present, such as:
        * "Edit Profile" (link to F1.9)
        * "Account Settings" (potentially leading to F5.3 Change Password, F1.11 Deactivate)
        * "Log Out" (F1.10)
---
**Test Case ID:** TC_F5.1_03
**User Story ID:** F5.1
**Test Case Title:** Verify Settings screen contains options/links for preferences
**Priority:** Medium
**Preconditions:**
    * User is on the main Settings screen (TC_F5.1_01).
**Test Steps:**
    1. Observe the sections and options listed on the Settings screen.
**Test Data:**
    * N/A
**Expected Results:**
    * Options related to user preferences are present, such as:
        * "Notification Settings" (link to F5.2 controls)
        * "Account Visibility" / "Privacy Settings" (link to F5.2 controls)
        * Potentially links to manage Premium subscription (if applicable).
---
**Test Case ID:** TC_F5.1_04
**User Story ID:** F5.1
**Test Case Title:** Verify Settings screen contains options for legal docs and app version
**Priority:** High
**Preconditions:**
    * User is on the main Settings screen (TC_F5.1_01).
**Test Steps:**
    1. Observe the sections and options listed on the Settings screen, potentially scrolling to the bottom or looking in an "About" section.
**Test Data:**
    * N/A
**Expected Results:**
    * Links to legal documents are present:
        * "Privacy Policy" (link to F5.5)
        * "Terms of Service" (link to F5.5)
        * "Licenses" (optional, link to F5.5)
    * The application's version number is displayed (F5.6).
---
**Test Case ID:** TC_F5.2_01
**User Story ID:** F5.2
**Test Case Title:** Verify Notification Settings screen shows toggles for New Matches and New Messages
**Priority:** Medium
**Preconditions:**
    * User is on the main Settings screen (F5.1).
    * A "Notification Settings" option exists.
**Test Steps:**
    1. Tap "Notification Settings".
    2. Observe the options presented on the Notification Settings screen.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is navigated to the Notification Settings screen.
    * Toggles or similar controls are visible for enabling/disabling specific notification types, including at least:
        * "New Matches"
        * "New Messages"
---
**Test Case ID:** TC_F5.2_02
**User Story ID:** F5.2
**Test Case Title:** Verify disabling a notification preference stops its delivery
**Priority:** Medium
**Preconditions:**
    * User is on the Notification Settings screen (TC_F5.2_01).
    * User has matched with User B.
    * Push notifications (F3.5) are functional.
    * The "New Messages" notification toggle is currently ON.
**Test Steps:**
    1. Toggle the "New Messages" notification setting to OFF.
    2. Save the settings (if required).
    3. Background the Mockaccino app.
    4. Have User B send a message to the user.
    5. Observe the user's device for push notifications.
**Test Data:**
    * Setting: New Messages = OFF
**Expected Results:**
    * The setting change is saved.
    * When User B sends a message, the user does *not* receive a push notification for the new message.
    * (Optional) Check if in-app indicators (unread count on tab) still update if the app is open.
---
**Test Case ID:** TC_F5.2_03
**User Story ID:** F5.2
**Test Case Title:** Verify enabling a notification preference allows its delivery
**Priority:** Medium
**Preconditions:**
    * User is on the Notification Settings screen (TC_F5.2_01).
    * User has matched with User B.
    * Push notifications (F3.5) are functional.
    * The "New Messages" notification toggle is currently OFF (from TC_F5.2_02).
**Test Steps:**
    1. Toggle the "New Messages" notification setting to ON.
    2. Save the settings (if required).
    3. Background the Mockaccino app.
    4. Have User B send another message to the user.
    5. Observe the user's device for push notifications.
**Test Data:**
    * Setting: New Messages = ON
**Expected Results:**
    * The setting change is saved.
    * When User B sends a message, the user *does* receive a push notification for the new message.
---
**Test Case ID:** TC_F5.2_04
**User Story ID:** F5.2
**Test Case Title:** Verify Account Visibility settings screen shows defined controls (Example: Pause Account)
**Priority:** Low
**Preconditions:**
    * User is on the main Settings screen (F5.1).
    * An "Account Visibility" or "Privacy Settings" option exists.
    * Specific visibility controls (e.g., "Pause Account" toggle) have been defined and implemented.
**Test Steps:**
    1. Tap "Account Visibility" / "Privacy Settings".
    2. Observe the options presented.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is navigated to the Account Visibility screen.
    * The defined controls are visible (e.g., a toggle labeled "Pause Account" or "Hide my profile").
---
**Test Case ID:** TC_F5.2_05
**User Story ID:** F5.2
**Test Case Title:** Verify changing account visibility setting prevents profile discovery (Example: Pause Account)
**Priority:** Low
**Preconditions:**
    * User A is on the Account Visibility settings screen (TC_F5.2_04).
    * The "Pause Account" toggle is currently OFF.
    * User B is logged in and potentially able to see User A in matching (F2.1).
**Test Steps:**
    1. User A toggles "Pause Account" to ON.
    2. User A saves the setting (if required).
    3. User B navigates to the main matching screen (F2.1) and swipes through profiles.
**Test Data:**
    * Setting: Pause Account = ON
**Expected Results:**
    * User A's visibility status is updated.
    * User B does *not* see User A's profile card in the matching queue while User A's account is paused.
---
**Test Case ID:** TC_F5.3_01
**User Story ID:** F5.3
**Test Case Title:** Verify "Change Password" option is available in Settings for email users
**Priority:** Medium
**Preconditions:**
    * User is logged in using their Email and Password (not SSO).
    * User is on the main Settings screen (F5.1).
**Test Steps:**
    1. Look for an option related to password management, possibly under "Account Settings".
**Test Data:**
    * N/A
**Expected Results:**
    * An option labeled "Change Password" is visible and accessible.
    * (Optional) This option might be hidden or disabled for users logged in via SSO (Apple/LinkedIn).
---
**Test Case ID:** TC_F5.3_02
**User Story ID:** F5.3
**Test Case Title:** Verify accessing "Change Password" requires entering the current password
**Priority:** Medium
**Preconditions:**
    * User is logged in via email/password.
    * User is on the Settings screen and taps "Change Password".
**Test Steps:**
    1. Observe the screen presented after tapping "Change Password".
**Test Data:**
    * N/A
**Expected Results:**
    * The user is navigated to the Change Password screen.
    * The screen includes an input field specifically for entering the "Current Password".
    * Fields for "New Password" and "Confirm New Password" might also be present, potentially disabled until the current password is verified.
---
**Test Case ID:** TC_F5.3_03
**User Story ID:** F5.3
**Test Case Title:** Verify entering correct current password enables new password fields
**Priority:** Medium
**Preconditions:**
    * User is on the Change Password screen (TC_F5.3_02).
    * New password fields might be initially disabled.
**Test Steps:**
    1. Enter the correct current password into the "Current Password" field.
    2. Observe the state of the "New Password" and "Confirm New Password" fields.
**Test Data:**
    * Current Password: CorrectPassword123!
**Expected Results:**
    * After entering the correct current password (and potentially moving focus or validation occurring), the "New Password" and "Confirm New Password" fields become enabled and editable.
---
**Test Case ID:** TC_F5.3_04
**User Story ID:** F5.3
**Test Case Title:** Verify successful password change with valid new password
**Priority:** High
**Preconditions:**
    * User is on the Change Password screen.
    * User has entered the correct current password.
    * New password fields are enabled.
**Test Steps:**
    1. Enter a new strong password into the "New Password" field.
    2. Enter the same new strong password into the "Confirm New Password" field.
    3. Tap the "Save" or "Update Password" button.
**Test Data:**
    * Current Password: CorrectPassword123!
    * New Password: NewStrongPassword456!
    * Confirm New Password: NewStrongPassword456!
**Expected Results:**
    * A success message is displayed (e.g., "Password updated successfully").
    * The user might be navigated back to the main Settings screen.
    * The account's password is changed in the backend.
---
**Test Case ID:** TC_F5.3_05
**User Story ID:** F5.3
**Test Case Title:** Verify error message if incorrect current password is entered
**Priority:** High
**Preconditions:**
    * User is on the Change Password screen (TC_F5.3_02).
**Test Steps:**
    1. Enter an *incorrect* password into the "Current Password" field.
    2. Enter a new password and confirm it.
    3. Tap the "Save" or "Update Password" button.
**Test Data:**
    * Current Password: IncorrectPassword!!!
    * New Password: NewStrongPassword456!
    * Confirm New Password: NewStrongPassword456!
**Expected Results:**
    * An error message is displayed indicating the current password was incorrect (e.g., "Incorrect current password").
    * The password is not changed.
    * The user remains on the Change Password screen.
---
**Test Case ID:** TC_F5.3_06
**User Story ID:** F5.3
**Test Case Title:** Verify error message if new passwords do not match
**Priority:** High
**Preconditions:**
    * User is on the Change Password screen.
    * User has entered the correct current password.
    * New password fields are enabled.
**Test Steps:**
    1. Enter a new strong password into the "New Password" field.
    2. Enter a *different* password into the "Confirm New Password" field.
    3. Tap the "Save" or "Update Password" button.
**Test Data:**
    * Current Password: CorrectPassword123!
    * New Password: NewStrongPassword456!
    * Confirm New Password: MismatchingPassword789?
**Expected Results:**
    * An error message is displayed indicating the new passwords do not match (e.g., "New passwords do not match").
    * The password is not changed.
    * The user remains on the Change Password screen.
---
**Test Case ID:** TC_F5.3_07
**User Story ID:** F5.3
**Test Case Title:** Verify error message or feedback if new password does not meet complexity requirements
**Priority:** Medium
**Preconditions:**
    * User is on the Change Password screen.
    * User has entered the correct current password.
    * New password fields are enabled.
    * Password complexity rules are defined (e.g., minimum length, characters).
**Test Steps:**
    1. Enter a new password that does *not* meet complexity rules (e.g., "weak") into the "New Password" field.
    2. Enter the same weak password into the "Confirm New Password" field.
    3. Tap the "Save" or "Update Password" button.
**Test Data:**
    * Current Password: CorrectPassword123!
    * New Password: weak
    * Confirm New Password: weak
**Expected Results:**
    * An error message is displayed indicating the new password does not meet requirements (e.g., "Password must be at least 8 characters long and include a number").
    * OR, inline validation feedback appears near the password field.
    * The password is not changed.
---
**Test Case ID:** TC_F5.3_08
**User Story ID:** F5.3
**Test Case Title:** Verify user can log in using the new password after successful change
**Priority:** High
**Preconditions:**
    * User has successfully changed their password (TC_F5.3_04).
    * User has logged out (F1.10).
    * User is on the login screen (F1.4).
**Test Steps:**
    1. Enter the user's email address.
    2. Enter the *new* password (set in TC_F5.3_04) into the password field.
    3. Tap the "Log In" button.
**Test Data:**
    * Email: user_email@example.com
    * Password: NewStrongPassword456!
**Expected Results:**
    * Login is successful.
    * The user is navigated to the main matching screen (F2.1).
---
**Test Case ID:** TC_F5.4_01
**User Story ID:** F5.4
**Test Case Title:** Verify Invite Code is displayed in Settings screen
**Priority:** Low
**Preconditions:**
    * User is logged in.
    * Invite Code feature (generation/assignment) is implemented.
    * User has been assigned an Invite Code.
    * User is on the main Settings screen (F5.1).
**Test Steps:**
    1. Look for a section or field related to "Invite Code" or "Referrals".
**Test Data:**
    * User's assigned Invite Code (e.g., "MOCKA123").
**Expected Results:**
    * The user's unique Invite Code (e.g., "MOCKA123") is displayed clearly on the Settings screen.
---
**Test Case ID:** TC_F5.4_02
**User Story ID:** F5.4
**Test Case Title:** Verify Invite Code is readable and potentially has a Copy button
**Priority:** Low
**Preconditions:**
    * User's Invite Code is displayed on the Settings screen (TC_F5.4_01).
**Test Steps:**
    1. Observe the displayed Invite Code and its surrounding elements.
**Test Data:**
    * N/A
**Expected Results:**
    * The code is displayed in a way that is easy to read and transcribe.
    * A "Copy" button or icon may be present next to the code.
---
**Test Case ID:** TC_F5.4_03
**User Story ID:** F5.4
**Test Case Title:** Verify tapping Copy button copies code to clipboard
**Priority:** Low
**Preconditions:**
    * User's Invite Code is displayed on the Settings screen (TC_F5.4_01).
    * A "Copy" button is present next to the code (TC_F5.4_02).
**Test Steps:**
    1. Tap the "Copy" button.
    2. Switch to another app with a text input field (e.g., Notes, Messages).
    3. Paste the content from the clipboard into the text field.
**Test Data:**
    * User's Invite Code: MOCKA123
**Expected Results:**
    * Tapping the "Copy" button provides feedback (e.g., briefly changes appearance, shows a "Copied!" message).
    * Pasting into another app inserts the exact Invite Code ("MOCKA123") that was displayed.
---
**Test Case ID:** TC_F5.5_01
**User Story ID:** F5.5
**Test Case Title:** Verify links for legal documents are present in Settings
**Priority:** High
**Preconditions:**
    * User is on the main Settings screen (F5.1).
**Test Steps:**
    1. Look for a "Legal" or "About" section, or scan the main list of settings options.
**Test Data:**
    * N/A
**Expected Results:**
    * Links/options labeled "Privacy Policy", "Terms of Service", and potentially "Licenses" are visible.
---
**Test Case ID:** TC_F5.5_02
**User Story ID:** F5.5
**Test Case Title:** Verify tapping "Privacy Policy" link displays the document
**Priority:** Medium
**Preconditions:**
    * User is on the Settings screen.
    * The "Privacy Policy" link is visible (TC_F5.5_01).
**Test Steps:**
    1. Tap the "Privacy Policy" link.
**Test Data:**
    * N/A
**Expected Results:**
    * The Privacy Policy document is displayed (e.g., in an in-app webview or browser).
    * The user can scroll and read the policy content.
---
**Test Case ID:** TC_F5.5_03
**User Story ID:** F5.5
**Test Case Title:** Verify tapping "Terms of Service" link displays the document
**Priority:** Medium
**Preconditions:**
    * User is on the Settings screen.
    * The "Terms of Service" link is visible (TC_F5.5_01).
**Test Steps:**
    1. Tap the "Terms of Service" link.
**Test Data:**
    * N/A
**Expected Results:**
    * The Terms of Service document is displayed (e.g., in an in-app webview or browser).
    * The user can scroll and read the terms content.
---
**Test Case ID:** TC_F5.5_04
**User Story ID:** F5.5
**Test Case Title:** Verify tapping "Licenses" link displays open-source license information
**Priority:** Low
**Preconditions:**
    * User is on the Settings screen.
    * The "Licenses" or "Acknowledgements" link is visible (TC_F5.5_01).
**Test Steps:**
    1. Tap the "Licenses" link.
**Test Data:**
    * N/A
**Expected Results:**
    * A screen or view displaying information about open-source software used in the app and their respective licenses is shown.
---
**Test Case ID:** TC_F5.6_01
**User Story ID:** F5.6
**Test Case Title:** Verify application version number is displayed in Settings
**Priority:** High
**Preconditions:**
    * User is on the main Settings screen (F5.1).
**Test Steps:**
    1. Look at the bottom of the Settings screen or within an "About" section.
**Test Data:**
    * Current app build version (e.g., 1.0.0 build 123).
**Expected Results:**
    * The application's version number is displayed clearly (e.g., "Version 1.0.0 (123)").
---
**Test Case ID:** TC_F5.7_01
**User Story ID:** F5.7
**Test Case Title:** Verify "Notifications" tab or access point is present
**Priority:** Medium
**Preconditions:**
    * User is logged in.
    * Notification Center feature (F5.7) is implemented.
**Test Steps:**
    1. Observe the main app navigation interface (tab bar, menu).
**Test Data:**
    * N/A
**Expected Results:**
    * A distinct "Notifications" tab or access point (e.g., a bell icon) is visible.
---
**Test Case ID:** TC_F5.7_02
**User Story ID:** F5.7
**Test Case Title:** Verify Notification Center displays recent activities chronologically
**Priority:** Medium
**Preconditions:**
    * User is logged in.
    * User has recently received several notifications (e.g., New Match with User B at 10:00 AM, New Message from User C at 10:05 AM, New Match with User D at 10:10 AM).
    * User navigates to the Notification Center (TC_F5.7_01).
**Test Steps:**
    1. Tap the "Notifications" access point.
    2. Observe the list of notifications displayed.
**Test Data:**
    * Notifications: Match B (10:00), Message C (10:05), Match D (10:10).
**Expected Results:**
    * The Notification Center screen is displayed.
    * A list of recent activities appears.
    * The list is ordered chronologically, with the newest event at the top (Match D, then Message C, then Match B).
---
**Test Case ID:** TC_F5.7_03
**User Story ID:** F5.7
**Test Case Title:** Verify "New Match" notification entry displays user name/picture and timestamp
**Priority:** Medium
**Preconditions:**
    * User is viewing the Notification Center list (TC_F5.7_02).
    * An entry for a "New Match" with User B is present in the list.
**Test Steps:**
    1. Observe the details shown within the "New Match" notification entry for User B.
**Test Data:**
    * Matched User: User B (Name, Picture)
    * Timestamp: 10:00 AM
**Expected Results:**
    * The entry clearly indicates it's a new match.
    * It displays User B's name and profile picture.
    * It displays the timestamp when the match occurred (10:00 AM).
---
**Test Case ID:** TC_F5.7_04
**User Story ID:** F5.7
**Test Case Title:** Verify "New Message" notification entry displays sender name/picture, snippet, and timestamp
**Priority:** Medium
**Preconditions:**
    * User is viewing the Notification Center list (TC_F5.7_02).
    * An entry for a "New Message" from User C is present in the list.
**Test Steps:**
    1. Observe the details shown within the "New Message" notification entry from User C.
**Test Data:**
    * Sender: User C (Name, Picture)
    * Message Snippet: "Hey there,..."
    * Timestamp: 10:05 AM
**Expected Results:**
    * The entry clearly indicates it's a new message.
    * It displays the sender's (User C's) name and profile picture.
    * It displays a snippet of the message content ("Hey there,...").
    * It displays the timestamp when the message was received (10:05 AM).
---
**Test Case ID:** TC_F5.7_05
**User Story ID:** F5.7
**Test Case Title:** Verify tapping a "New Match" notification navigates appropriately
**Priority:** Medium
**Preconditions:**
    * User is viewing the Notification Center list (TC_F5.7_02).
    * An entry for a "New Match" with User B is present.
**Test Steps:**
    1. Tap on the "New Match" notification entry for User B.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is navigated away from the Notification Center.
    * EITHER: The user is navigated to the chat screen (F3.4) with User B.
    * OR: The user is navigated to User B's profile screen (F1.8). (Behavior depends on design choice).
---
**Test Case ID:** TC_F5.7_06
**User Story ID:** F5.7
**Test Case Title:** Verify tapping a "New Message" notification navigates to the corresponding chat screen
**Priority:** Medium
**Preconditions:**
    * User is viewing the Notification Center list (TC_F5.7_02).
    * An entry for a "New Message" from User C is present.
**Test Steps:**
    1. Tap on the "New Message" notification entry from User C.
**Test Data:**
    * N/A
**Expected Results:**
    * The user is navigated away from the Notification Center.
    * The user is navigated directly to the chat screen (F3.4) with User C.
---
**Test Case ID:** TC_F5.7_07
**User Story ID:** F5.7
**Test Case Title:** Verify unread notifications are visually distinct in Notification Center
**Priority:** Low
**Preconditions:**
    * User is viewing the Notification Center list (TC_F5.7_02).
    * Some notifications in the list correspond to events the user has not yet interacted with (e.g., hasn't tapped the notification, hasn't visited the related chat/profile).
    * Some notifications correspond to events already seen/actioned.
**Test Steps:**
    1. Observe the appearance of unread notification entries.
    2. Observe the appearance of read notification entries.
**Test Data:**
    * N/A
**Expected Results:**
    * Unread notification entries have a visually distinct style compared to read entries (e.g., different background color, a persistent unread dot/indicator).
---
**Test Case ID:** TC_F5.7_08
**User Story ID:** F5.7
**Test Case Title:** Verify viewing/tapping a notification marks it as read in Notification Center
**Priority:** Low
**Preconditions:**
    * User is viewing the Notification Center list (TC_F5.7_02).
    * An unread notification entry (e.g., New Message from User C) is present and visually distinct (TC_F5.7_07).
**Test Steps:**
    1. Tap on the unread notification entry for User C.
    2. Navigate back to the Notification Center list.
    3. Observe the appearance of the notification entry for User C again.
    4. OR (Alternative): Simply viewing the Notification Center might mark all currently visible items as read (depends on implementation). Observe if unread indicators disappear after viewing the list.
**Test Data:**
    * N/A
**Expected Results:**
    * After tapping the notification (and returning), the entry for User C no longer appears visually distinct as unread. It now looks like a read notification.
    * OR (Alternative): After viewing the Notification Center, the unread indicators for all previously unread items might disappear.
---
**Test Case ID:** TC_F5.7_09
**User Story ID:** F5.7
**Test Case Title:** Verify Notification Center shows empty state if there are no notifications
**Priority:** Low
**Preconditions:**
    * User is logged in.
    * User has received no notifications (no new matches, no new messages since last check/clearing).
    * User navigates to the Notification Center (TC_F5.7_01).
**Test Steps:**
    1. Observe the content of the Notification Center screen.
**Test Data:**
    * N/A
**Expected Results:**
    * Instead of a list of notifications, an empty state message is displayed (e.g., "No new notifications", "You're all caught up!").
