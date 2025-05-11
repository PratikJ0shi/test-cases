# Login Functionality - Manual Test Cases

## Overview
This document contains 20 basic test cases for validating the Login functionality of a web application.

---

## login_testcases

| TC ID       | Test Case Title                         | Precondition           | Steps                                                                 | Expected Result                                      | Priority |
|-------------|------------------------------------------|------------------------|-----------------------------------------------------------------------|------------------------------------------------------|----------|
| TC_LOGIN_01 | Valid Login Credentials                  | User is registered     | Enter valid email and password, click Login                          | User is redirected to the dashboard/homepage         | High     |
| TC_LOGIN_02 | Invalid Password                         | User is registered     | Enter valid email and incorrect password, click Login                | "Invalid credentials" error is shown                 | High     |
| TC_LOGIN_03 | Invalid Email Format                     | -                      | Enter invalid email format, any password, click Login                | "Invalid email format" validation message            | Medium   |
| TC_LOGIN_04 | Unregistered Email                       | -                      | Enter email not linked to any account, any password, click Login     | "Account not found" error is shown                   | Medium   |
| TC_LOGIN_05 | Empty Email Field                        | -                      | Leave email empty, fill password, click Login                        | "Email is required" message is shown                 | Medium   |
| TC_LOGIN_06 | Empty Password Field                     | -                      | Fill email, leave password empty, click Login                        | "Password is required" message is shown              | Medium   |
| TC_LOGIN_07 | Both Fields Empty                        | -                      | Leave both email and password fields empty, click Login              | Both fields show validation errors                   | Medium   |
| TC_LOGIN_08 | Password Field Masking                   | -                      | Observe password input while typing                                  | Password characters are hidden (e.g., •••••)         | Low      |
| TC_LOGIN_09 | Show/Hide Password Toggle                | -                      | Click on show/hide icon on password field                            | Password visibility toggles correctly                | Low      |
| TC_LOGIN_10 | Login Button Disabled Initially          | -                      | Do not enter any data                                                | Login button should be disabled                      | Low      |
| TC_LOGIN_11 | Login Button Enabled After Input         | -                      | Enter valid inputs                                                   | Login button becomes enabled                         | Low      |
| TC_LOGIN_12 | SQL Injection in Email                   | -                      | Enter SQL code (`' OR 1=1 --`) in email field                        | Login is blocked, error shown                        | High     |
| TC_LOGIN_13 | SQL Injection in Password                | -                      | Enter SQL code in password field                                     | Login is blocked, error shown                        | High     |
| TC_LOGIN_14 | XSS in Email Field                       | -                      | Enter `<script>alert(1)</script>` in email field                     | Input is sanitized, no script runs                   | High     |
| TC_LOGIN_15 | Session Created Only on Success          | -                      | Try login with invalid credentials                                   | Session/cookie is not created                        | Medium   |
| TC_LOGIN_16 | Redirect to Last Visited Page After Login| User session expired   | Try accessing protected page, then login                             | Redirected to originally requested page              | Medium   |
| TC_LOGIN_17 | Remember Me Checkbox                     | -                      | Tick "Remember Me", login, close and reopen browser                  | User remains logged in                               | Medium   |
| TC_LOGIN_18 | Forgot Password Link Functional          | -                      | Click "Forgot Password"                                              | Redirects to password recovery page                  | Medium   |
| TC_LOGIN_19 | Error Message Disappears on Input Change | -                      | Trigger error, then modify input                                     | Error message disappears dynamically                 | Low      |
| TC_LOGIN_20 | Mobile Responsiveness                    | -                      | Open login page on mobile device                                     | Page adapts well, inputs and buttons are usable      | Low      |

---

## Notes
- All tests assume the application is accessible and the backend services are running.
- These test cases cover both UI and security perspectives for login.


---

# Login Functionality - Full Test Suite

## Overview
This document includes **20 positive** and **20 negative** test cases for validating the Login functionality of a web application.

---

## positive

| TC ID       | Title                                       | Precondition             | Steps                                                                 | Expected Result                                      | Priority |
|-------------|---------------------------------------------|--------------------------|-----------------------------------------------------------------------|------------------------------------------------------|----------|
| TC_POS_01   | Valid Login                                 | Registered user          | Enter valid email and password, click Login                          | User redirected to dashboard                         | High     |
| TC_POS_02   | Remember Me works                           | Registered user          | Select "Remember Me", login, close and reopen browser                | User remains logged in                               | Medium   |
| TC_POS_03   | Redirect after login                        | User session expired     | Access protected page, login                                         | Redirects to that page                               | Medium   |
| TC_POS_04   | Show Password toggle                        | -                        | Click eye icon on password field                                     | Password becomes visible                             | Low      |
| TC_POS_05   | Password masking                            | -                        | Enter password                                                       | Password is hidden (dots or bullets)                 | Low      |
| TC_POS_06   | Case-insensitive email                      | Registered user          | Enter valid email in UPPERCASE                                       | Login succeeds                                       | Medium   |
| TC_POS_07   | Special characters in password              | Registered user          | Enter valid password with symbols                                    | Login succeeds                                       | Medium   |
| TC_POS_08   | Auto-focus on email field                   | -                        | Open login page                                                      | Cursor auto-focused in email field                  | Low      |
| TC_POS_09   | Keyboard Enter submits form                 | Registered user          | Enter credentials, press Enter                                       | Login is submitted                                   | Low      |
| TC_POS_10   | Mobile responsiveness                       | -                        | Open login page on mobile                                            | Page is responsive                                   | Low      |
| TC_POS_11   | Multi-browser compatibility                 | -                        | Open login in Chrome, Firefox, Safari                                | Login works on all                                  | Low      |
| TC_POS_12   | Password copy-paste allowed                 | -                        | Paste password into field                                            | Login works                                          | Low      |
| TC_POS_13   | Email field accepts valid format            | -                        | Enter standard email format                                          | Accepted without error                              | Medium   |
| TC_POS_14   | Session token generated after login         | -                        | Log in and inspect cookies/session                                   | Session/token is created                            | Medium   |
| TC_POS_15   | User lands on correct dashboard             | Registered user          | Log in successfully                                                  | Redirected to user's dashboard/home                  | High     |
| TC_POS_16   | Language selector updates labels            | -                        | Change language on login page                                        | Labels and messages translate correctly              | Low      |
| TC_POS_17   | Login with autofill                         | Registered user          | Use browser-saved credentials                                        | Login works                                          | Low      |
| TC_POS_18   | Accessibility - Screen reader reads labels  | -                        | Use screen reader on login page                                      | Labels and inputs are read out                       | Low      |
| TC_POS_19   | Forgot password link redirects properly     | -                        | Click "Forgot Password"                                              | Redirects to reset page                              | Medium   |
| TC_POS_20   | Terms & Privacy links open correctly        | -                        | Click footer links                                                   | Opens correct legal pages                            | Low      |

---

## negative

| TC ID       | Title                                       | Precondition             | Steps                                                                 | Expected Result                                      | Priority |
|-------------|---------------------------------------------|--------------------------|-----------------------------------------------------------------------|------------------------------------------------------|----------|
| TC_NEG_01   | Empty email and password                    | -                        | Click Login without entering anything                                | Show required field errors                           | High     |
| TC_NEG_02   | Empty email only                            | -                        | Leave email empty, enter password                                    | "Email is required" message shown                    | Medium   |
| TC_NEG_03   | Empty password only                         | -                        | Enter email, leave password blank                                    | "Password is required" message shown                 | Medium   |
| TC_NEG_04   | Invalid password                            | Registered user          | Enter valid email, wrong password                                    | "Invalid credentials" error                          | High     |
| TC_NEG_05   | Invalid email format                        | -                        | Enter `user@wrong` format                                            | Email validation error                               | Medium   |
| TC_NEG_06   | Unregistered email                          | -                        | Enter unknown email with password                                    | "Account not found" error                            | Medium   |
| TC_NEG_07   | SQL injection in email                      | -                        | Enter `' OR 1=1 --` in email                                         | Login blocked or error shown                         | High     |
| TC_NEG_08   | SQL injection in password                   | -                        | Enter `' OR '1'='1` in password                                      | Login blocked or error shown                         | High     |
| TC_NEG_09   | XSS script in email field                   | -                        | Enter `<script>alert(1)</script>` in email                           | Input sanitized or rejected                          | High     |
| TC_NEG_10   | Extra spaces in email                       | -                        | Enter email with leading/trailing spaces                            | Trimmed or error shown                               | Medium   |
| TC_NEG_11   | Extra spaces in password                    | -                        | Enter correct password with spaces                                  | Login fails                                          | Medium   |
| TC_NEG_12   | Enter emoji in email                        | -                        | Paste emoji into email field                                         | Validation error                                     | Low      |
| TC_NEG_13   | Copy-paste invalid password                 | -                        | Paste wrong password                                                 | Login fails                                          | Low      |
| TC_NEG_14   | Browser back after login - session gone     | Logged out               | Login, logout, press back                                            | Should not access dashboard                          | Medium   |
| TC_NEG_15   | Password field accepts less than min chars  | -                        | Enter 2-character password                                           | Validation message shown                             | Medium   |
| TC_NEG_16   | Email exceeds max length                    | -                        | Enter 300+ characters in email                                       | Error or trimmed                                     | Low      |
| TC_NEG_17   | Password exceeds max length                 | -                        | Enter 300+ characters in password                                    | Error or blocked                                     | Low      |
| TC_NEG_18   | Login while already logged in               | -                        | Try logging in again in new tab                                     | Redirects or error                                   | Low      |
| TC_NEG_19   | Session timeout before login                | -                        | Wait on login page till session expires, then login                  | Session renewed or redirected                        | Low      |
| TC_NEG_20   | Brute force multiple failed attempts        | -                        | Enter wrong password 5 times                                         | Account lock or captcha shown                        | High     |

---


# Login Module - Categorized Test Cases (Detailed)

This document contains **15 detailed test cases each** for the following types of testing:
- Sanity
- Smoke
- Retesting
- Regression
- End-to-End (E2E)

---

## sanity

> Quick checks after each build to verify core functionality before proceeding to deeper testing.

| TC ID     | Title                             | Steps                                                                 | Expected Result                                      |
|-----------|-----------------------------------|-----------------------------------------------------------------------|------------------------------------------------------|
| SAN_01    | Launch application                | Open the URL or app                                                  | Login screen loads without error                    |
| SAN_02    | UI Elements present               | Check email, password fields and login button                        | All elements are visible and aligned                |
| SAN_03    | Email input functional            | Type text in email field                                             | Text appears correctly                              |
| SAN_04    | Password input functional         | Type text in password field                                          | Text is masked and appears correctly                |
| SAN_05    | Login button enabled              | Fill valid inputs                                                    | Login button becomes clickable                      |
| SAN_06    | Login button disabled             | Leave inputs empty                                                   | Login button stays disabled                         |
| SAN_07    | Click Login                       | Enter valid credentials, click login                                 | User redirected to dashboard                        |
| SAN_08    | Error on empty email              | Leave email empty, click login                                       | "Email is required" error shown                     |
| SAN_09    | Error on empty password           | Leave password empty, click login                                    | "Password is required" error shown                  |
| SAN_10    | Show/Hide Password toggle         | Click on eye icon in password field                                  | Toggles visibility                                  |
| SAN_11    | Forgot password link present      | Check below password field                                           | "Forgot Password?" is visible and clickable         |
| SAN_12    | Page loads under 3 seconds        | Refresh login page                                                   | Loads within performance threshold                  |
| SAN_13    | Tab order navigation              | Use tab key on keyboard                                              | Focus moves field-by-field logically                |
| SAN_14    | Label alignment                   | Check labels for each field                                          | Labels aligned to respective input fields           |
| SAN_15    | Field placeholders visible        | Check input fields                                                   | Placeholders like "Enter Email" are visible         |

---

## smoke

> High-level functional checks to verify stability of major flows.

| TC ID     | Title                             | Steps                                                                 | Expected Result                                      |
|-----------|-----------------------------------|-----------------------------------------------------------------------|------------------------------------------------------|
| SMK_01    | Login with valid credentials      | Enter correct email & password                                       | User logs in successfully                           |
| SMK_02    | Forgot Password link              | Click the link                                                       | Redirects to password recovery page                 |
| SMK_03    | Reset password via email          | Trigger reset → Check email → Reset password                         | Password successfully updated                       |
| SMK_04    | Logout functionality              | Log in → Click Logout                                                | User is redirected to login screen                  |
| SMK_05    | Session token created             | Log in, inspect browser session storage                              | Token/session is active                             |
| SMK_06    | Session timeout works             | Idle after login for x mins                                          | Auto logout or warning shown                        |
| SMK_07    | Access profile page after login   | Log in → Go to profile                                               | Profile page loads                                  |
| SMK_08    | Email format accepted             | Enter valid format (e.g., `user@example.com`)                        | No validation error                                 |
| SMK_09    | Login button responsive           | Click login button                                                   | System responds immediately                         |
| SMK_10    | UI loads correctly on mobile      | Open login on mobile browser                                         | Layout adjusts, no overlapping elements             |
| SMK_11    | Access restricted page while logged out | Try to open dashboard directly                                 | Redirects to login                                  |
| SMK_12    | Error on invalid credentials      | Enter wrong credentials                                              | "Invalid credentials" message shown                 |
| SMK_13    | Caps Lock warning in password     | Enable Caps Lock, enter password                                     | Warning shown (if implemented)                      |
| SMK_14    | Auto-focus on email field         | Load login page                                                      | Email input is auto-focused                         |
| SMK_15    | Branding and title present        | Check header/title                                                   | Company logo and login title are visible            |

---

## retesting

> Re-execution of failed test cases after defect fixes.

| TC ID     | Title                             | Steps                                                                 | Expected Result                                      |
|-----------|-----------------------------------|-----------------------------------------------------------------------|------------------------------------------------------|
| RET_01    | Correct error on invalid login    | Enter wrong password                                                 | Proper error shown                                  |
| RET_02    | Password reset sends email        | Enter valid registered email on reset page                           | Reset email received                                |
| RET_03    | Forgot password flow fixed        | Follow full reset flow after bug fix                                 | Password reset and login successful                 |
| RET_04    | Empty input validation works      | Submit form with empty fields                                        | Required field error shown                          |
| RET_05    | SQL injection blocked             | Enter `' OR 1=1 --` in fields                                        | Login fails, inputs sanitized                       |
| RET_06    | Special characters accepted       | Enter complex but valid password                                     | Login succeeds                                      |
| RET_07    | Browser compatibility             | Run login on Safari/Edge                                             | All steps work the same                             |
| RET_08    | UI alignment fixed                | Check field alignment after layout bug                               | All elements aligned correctly                      |
| RET_09    | Email trimming implemented        | Enter email with spaces                                              | Spaces trimmed automatically                        |
| RET_10    | Login with changed password       | Reset password → Try logging in                                      | Login successful                                    |
| RET_11    | Field validation message updated  | Enter invalid email                                                  | New validation message displayed                    |
| RET_12    | Redirect bug fixed                | Access dashboard unauthenticated                                     | Redirects to login page                             |
| RET_13    | Session expiry issue resolved     | Wait beyond timeout                                                  | Auto logout works                                   |
| RET_14    | Click login twice issue fixed     | Double click login                                                   | Single request processed                            |
| RET_15    | Password length enforcement       | Try short password                                                   | Validation triggers appropriately                   |

---

## regression

> Ensure new features or bug fixes didn’t break existing functionality.

| TC ID     | Title                             | Steps                                                                 | Expected Result                                      |
|-----------|-----------------------------------|-----------------------------------------------------------------------|------------------------------------------------------|
| REG_01    | Login still works after updates   | Enter valid credentials                                              | Successful login                                     |
| REG_02    | Logout still functional           | Click logout                                                         | Returns to login screen                             |
| REG_03    | Error messages consistent         | Enter wrong password                                                 | Same error shown as before                          |
| REG_04    | UI styles retained                | Inspect input and button styles                                      | Matches original design                             |
| REG_05    | Email field validations intact    | Try invalid format                                                   | Email error shown                                   |
| REG_06    | Required fields still validated   | Leave email/password empty                                           | Validation shown                                    |
| REG_07    | Page loads under 3s               | Load login after update                                              | Still performs fast                                 |
| REG_08    | Password reset process unchanged  | Complete forgot password flow                                        | Works as before                                     |
| REG_09    | Terms & Privacy links work        | Click footer links                                                   | Open in new tab                                     |
| REG_10    | Autofill still supported          | Use saved browser credentials                                        | Autofill works                                      |
| REG_11    | Password masking persists         | Observe password field                                               | Still masked                                        |
| REG_12    | Browser tab title unchanged       | Check browser tab                                                    | Title reads "Login"                                 |
| REG_13    | Forgot password redirect intact   | Click forgot link                                                    | Goes to correct page                                |
| REG_14    | Show password toggle functional   | Use eye icon                                                         | Shows/hides input                                   |
| REG_15    | Case-insensitive login            | Enter email in UPPERCASE                                             | Login successful                                    |

---

## e2e

> Covers real-world scenarios from login to logout or feature interaction.

| TC ID     | Title                             | Steps                                                                 | Expected Result                                      |
|-----------|-----------------------------------|-----------------------------------------------------------------------|------------------------------------------------------|
| E2E_01    | Login → Dashboard view            | Log in                                                               | User lands on dashboard                             |
| E2E_02    | Login → View profile              | Log in → Click Profile                                               | Profile opens with user info                        |
| E2E_03    | Login → Edit profile              | Log in → Go to Profile → Edit info → Save                           | Changes reflect successfully                        |
| E2E_04    | Login → Change password           | Navigate to Settings → Change Password                              | New password saved                                  |
| E2E_05    | Login → Logout                    | Log in → Perform actions → Logout                                    | User returns to login page                          |
| E2E_06    | Invalid login → Retry → Success   | Fail login once → Retry with correct creds                           | Login successful                                    |
| E2E_07    | Login → Cart → Checkout           | Log in → Add item → Proceed to checkout                              | Order placed                                        |
| E2E_08    | Login → Dashboard → Analytics     | Log in → Navigate to analytics dashboard                             | Charts/data load correctly                          |
| E2E_09    | Login → Upload Profile Picture    | Log in → Go to Profile → Upload image                                | Image updates                                       |
| E2E_10    | Login → Notification Settings     | Log in → Settings → Notifications → Update preference                | Preference saved                                    |
| E2E_11    | Login → Password reset → Re-login | Forgot Password → Reset → Use new password                           | Login successful with updated password              |
| E2E_12    | Login → Search feature            | Log in → Use search to find item                                     | Results shown                                       |
| E2E_13    | Login → Form submission           | Log in → Fill contact/support form                                   | Confirmation shown                                  |
| E2E_14    | Login → Access file/download      | Log in → Download file from dashboard                                | File downloads                                      |
| E2E_15    | Login → Navigate tabs → Logout    | Log in → Browse various app tabs → Logout                            | All transitions smooth, ends with logout            |

---
**Prepared by:** [Pratik Joshi]   
**Module:** | Form Testing | login-testcases |
