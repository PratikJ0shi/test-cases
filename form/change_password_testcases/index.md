## change_password_testcases

---

| TC ID     | Test Scenario                                       | Test Steps                                                                                  | Expected Result                                                       | Priority |
|-----------|------------------------------------------------------|----------------------------------------------------------------------------------------------|------------------------------------------------------------------------|----------|
| TC_CP_01  | Access change password page                          | Login > Navigate to profile > Click "Change Password"                                       | Change password page loads                                           | High     |
| TC_CP_02  | All required fields are present                      | Open change password form                                                                   | Old Password, New Password, Confirm Password fields are visible       | High     |
| TC_CP_03  | Submit with valid inputs                             | Enter valid old password, strong new password, and confirm                                  | Password successfully changed                                        | High     |
| TC_CP_04  | Login with new password                              | Logout > Login with new password                                                            | Login successful                                                      | High     |
| TC_CP_05  | Submit blank old password                            | Leave old password blank and fill rest                                                      | Error: "Old password is required"                                    | High     |
| TC_CP_06  | Submit blank new password                            | Leave new password blank                                                                    | Error: "New password is required"                                    | High     |
| TC_CP_07  | Submit blank confirm password                        | Leave confirm password blank                                                                | Error: "Confirm password is required"                                | High     |
| TC_CP_08  | Mismatched new and confirm password                  | Enter different new and confirm passwords                                                   | Error: "Passwords do not match"                                      | High     |
| TC_CP_09  | Weak new password                                    | Enter password like "12345"                                                                 | Error: "Password is too weak"                                        | Medium   |
| TC_CP_10  | New password same as old password                    | Enter the same value in old and new password fields                                         | Error: "New password must differ from current password"              | Medium   |
| TC_CP_11  | Incorrect old password                               | Enter incorrect old password                                                                | Error: "Old password is incorrect"                                   | High     |
| TC_CP_12  | Password strength indicator visible                  | Start typing in new password field                                                          | Strength meter should appear and update live                         | Medium   |
| TC_CP_13  | Confirm password field masked                        | Check confirm password input field                                                          | Password is hidden with asterisks/dots                               | Low      |
| TC_CP_14  | Password fields have toggle show/hide option         | Click eye icon beside password fields                                                       | Input visibility toggles                                              | Low      |
| TC_CP_15  | Client-side validation before submit                 | Submit mismatched or empty values                                                           | Errors shown without server call                                     | Medium   |
| TC_CP_16  | Submit form with network off                         | Fill form > Turn off internet > Submit                                                      | Shows network error or retry message                                 | Medium   |
| TC_CP_17  | Session expired while submitting                     | Let session expire > Try submitting form                                                    | Redirected to login or error shown                                   | High     |
| TC_CP_18  | Submit form multiple times quickly                   | Click submit multiple times rapidly                                                         | Only one request processed; others ignored or blocked                | Medium   |
| TC_CP_19  | Success message displayed                            | Submit valid change password form                                                           | Success toast or message shown                                       | Medium   |
| TC_CP_20  | Redirection after successful password change         | Submit valid form > Wait for redirection                                                    | User redirected to login or dashboard with confirmation              | Medium   |

---

## posotive

| TC ID     | Test Scenario                                    | Test Steps                                                                                  | Expected Result                                                   | Priority |
|-----------|--------------------------------------------------|----------------------------------------------------------------------------------------------|------------------------------------------------------------------|----------|
| TC_CP_P01 | Valid password change                            | Enter correct old password, strong new password, confirm password                           | Password changed successfully                                     | High     |
| TC_CP_P02 | Login with new password                          | Change password > Logout > Login with new password                                          | Login successful                                                  | High     |
| TC_CP_P03 | Password strength validation                     | Enter strong password with mix of characters                                                | Password accepted                                                  | Medium   |
| TC_CP_P04 | Show/hide password toggle                        | Click eye icon on password field                                                            | Password visibility toggles                                       | Low      |
| TC_CP_P05 | Field validation before submit                   | Leave any field empty and try to submit                                                     | Error shown before form submission                                | Medium   |
| TC_CP_P06 | Success message on valid input                   | Submit correct form                                                                         | Success message shown                                              | Medium   |
| TC_CP_P07 | Confirm password matches new password            | Enter same new and confirm password                                                         | Form submits successfully                                          | High     |
| TC_CP_P08 | New password different from old                 | Use different values for old and new password                                               | Password updated                                                   | Medium   |
| TC_CP_P09 | Fast response from backend                       | Submit form and track response time                                                         | Response is timely (under 2s)                                     | Low      |
| TC_CP_P10 | Form resets after successful change              | Submit successfully                                                                         | Form fields reset/cleared                                          | Low      |
| TC_CP_P11 | Keyboard navigation supported                    | Tab through fields                                                                          | Cursor moves sequentially                                          | Low      |
| TC_CP_P12 | Confirm password masked                          | Check input behavior                                                                        | Password input is masked                                           | Low      |
| TC_CP_P13 | Proper label and placeholder shown               | View input fields                                                                           | Clear placeholder and label present                               | Low      |
| TC_CP_P14 | Responsive design for mobile                     | Open form on small screen                                                                   | Layout is mobile-friendly                                          | Medium   |
| TC_CP_P15 | Redirect after successful change                 | Submit valid password change                                                                | Redirected to login/dashboard                                     | Medium   |

---


## negative

| TC ID     | Test Scenario                                     | Test Steps                                                                                  | Expected Result                                                  | Priority |
|-----------|---------------------------------------------------|----------------------------------------------------------------------------------------------|------------------------------------------------------------------|----------|
| TC_CP_N01 | Submit blank form                                 | Leave all fields empty and submit                                                           | Show validation errors                                           | High     |
| TC_CP_N02 | Incorrect old password                            | Enter incorrect old password                                                                | Error: "Old password incorrect"                                  | High     |
| TC_CP_N03 | Weak new password                                 | Enter short/simple password like "1234"                                                     | Error: "Weak password"                                           | Medium   |
| TC_CP_N04 | New password same as old                          | Enter same values for old and new password                                                  | Error: "New password must be different"                          | Medium   |
| TC_CP_N05 | Mismatched new and confirm password               | Enter different new and confirm passwords                                                   | Error: "Passwords do not match"                                  | High     |
| TC_CP_N06 | Invalid characters in password                    | Use unsupported symbols like emojis                                                         | Error: "Invalid characters in password"                          | Medium   |
| TC_CP_N07 | New password too long                             | Enter password over max character limit                                                     | Error or input truncated                                         | Low      |
| TC_CP_N08 | Confirm password empty                            | Leave confirm password empty                                                                | Error shown                                                      | High     |
| TC_CP_N09 | Try submitting multiple times                     | Rapidly click submit                                                                        | Only one submission allowed                                      | Medium   |
| TC_CP_N10 | Network disconnect during submit                  | Turn off internet > Submit                                                                 | Error: "Network error"                                           | Medium   |
| TC_CP_N11 | Session expired before form submission            | Wait > Try to submit form                                                                   | Redirected to login page                                         | High     |
| TC_CP_N12 | HTML injection in input fields                    | Enter script in password fields                                                             | Inputs sanitized or error shown                                  | High     |
| TC_CP_N13 | SQL injection attempt                             | Enter SQL query as password                                                                 | Inputs rejected or error shown                                   | High     |
| TC_CP_N14 | Submit form with special characters only          | Use only special characters like "@@!!%%"                                                   | Error: "Password format not allowed"                             | Medium   |
| TC_CP_N15 | Navigate back from change password without save   | Fill form > Go back                                                                         | No password change happens                                       | Low      |

---

## smoke

| TC ID     | Test Scenario                                      | Test Steps                                                                 | Expected Result                                      | Priority |
|-----------|---------------------------------------------------|------------------------------------------------------------------------------|-----------------------------------------------------|----------|
| ST_TC_01  | Launch Application                                | Open URL in browser                                                          | Home page loads without error                       | High     |
| ST_TC_02  | Login functionality                               | Enter valid credentials and login                                            | Redirected to dashboard                             | High     |
| ST_TC_03  | Logout functionality                              | Click logout                                                                 | Redirected to login page                            | High     |
| ST_TC_04  | Registration page opens                           | Navigate to sign up page                                                     | Registration form displays                          | High     |
| ST_TC_05  | Submit contact form                               | Fill and submit contact form                                                 | Success message shown                               | Medium   |
| ST_TC_06  | Dashboard loads after login                       | Login with valid user                                                        | Dashboard content loads                             | High     |
| ST_TC_07  | Profile section loads                             | Click profile                                                                | Profile page opens                                  | Medium   |
| ST_TC_08  | Change password screen accessible                 | Go to profile > Change Password                                              | Form is displayed                                   | Medium   |
| ST_TC_09  | Search bar is visible                             | Go to homepage                                                               | Search bar appears                                  | Low      |
| ST_TC_10  | Pagination works                                  | Navigate to multi-page list                                                  | Pagination displays and works                       | Medium   |
| ST_TC_11  | Add to cart                                       | Click "Add to cart" on product                                               | Product added to cart                               | High     |
| ST_TC_12  | Checkout process initiates                        | Click checkout                                                               | Redirects to checkout                               | High     |
| ST_TC_13  | File upload works                                 | Upload a file                                                                | File uploaded successfully                          | Medium   |
| ST_TC_14  | Notification alert on action                      | Perform an action triggering notification                                    | Alert shown                                         | Low      |
| ST_TC_15  | OTP Verification trigger                          | Enter email and request OTP                                                  | OTP sent confirmation                               | High     |

---


## sanity

| TC ID     | Test Scenario                                      | Test Steps                                                                 | Expected Result                                      | Priority |
|-----------|---------------------------------------------------|------------------------------------------------------------------------------|-----------------------------------------------------|----------|
| SAN_TC_01 | Check if login works with new credentials         | Register > Login                                                             | User logged in                                      | High     |
| SAN_TC_02 | Verify password change reflects on login          | Change password > Logout > Login                                             | New password works                                  | High     |
| SAN_TC_03 | Registration form validation                      | Enter invalid email and submit                                               | Error message shown                                 | Medium   |
| SAN_TC_04 | Valid user role redirect                          | Login as admin                                                               | Redirect to admin dashboard                         | High     |
| SAN_TC_05 | Wishlist updates after item added                 | Add product to wishlist                                                      | Wishlist count increases                            | Medium   |
| SAN_TC_06 | Notifications for new orders                      | Place an order                                                               | Notification appears                                | Medium   |
| SAN_TC_07 | File upload shows preview                         | Upload image                                                                 | Preview is shown                                    | Medium   |
| SAN_TC_08 | Pagination on product list                        | Navigate through pages                                                       | Correct items shown                                 | Medium   |
| SAN_TC_09 | Sorting products                                  | Apply price low-high                                                         | List updates correctly                              | Medium   |
| SAN_TC_10 | OTP verified successfully                         | Submit OTP                                                                   | OTP verified and redirected                         | High     |
| SAN_TC_11 | Forgot password mail trigger                      | Enter email and click "forgot password"                                      | Reset mail sent                                     | High     |
| SAN_TC_12 | Admin panel access only to admin                  | Login as user and try accessing admin path                                   | Access denied or redirected                         | High     |
| SAN_TC_13 | Social login redirects                            | Click on Google login                                                        | Redirect to Google auth                             | Medium   |
| SAN_TC_14 | Change password validation                        | Try weak password                                                            | Error message shown                                 | Medium   |
| SAN_TC_15 | Checkout summary visibility                       | Go to checkout                                                               | Cart items shown with correct price                 | Medium   |

---

## retesting

| TC ID     | Test Scenario                                      | Test Steps                                                                 | Expected Result                                      | Priority |
|-----------|---------------------------------------------------|------------------------------------------------------------------------------|-----------------------------------------------------|----------|
| RT_TC_01  | Retest login after bug fix                        | Enter valid credentials                                                      | Login successful                                    | High     |
| RT_TC_02  | Retest logout                                     | Logout user                                                                  | User redirected to login                            | High     |
| RT_TC_03  | Retest password change issue                      | Submit correct old and new password                                          | Password changes successfully                       | High     |
| RT_TC_04  | Retest profile save issue                         | Update and save profile                                                      | Data saved correctly                                | Medium   |
| RT_TC_05  | Retest registration duplicate validation          | Try registering with existing email                                          | Proper error shown                                  | High     |
| RT_TC_06  | Retest forgot password mail delivery              | Request reset link                                                           | Email received                                      | High     |
| RT_TC_07  | Retest file upload UI                             | Upload large file                                                            | File uploads and displays preview                   | Medium   |
| RT_TC_08  | Retest cart persistence issue                     | Add to cart > Refresh page                                                   | Item still in cart                                  | Medium   |
| RT_TC_09  | Retest mobile responsiveness bug                  | Open on mobile                                                               | UI displays correctly                               | Medium   |
| RT_TC_10  | Retest notification alerts                        | Perform triggering action                                                    | Alert shown                                         | Low      |
| RT_TC_11  | Retest email format validation                    | Enter malformed email                                                        | Validation error shown                              | Medium   |
| RT_TC_12  | Retest social login error                         | Use Google login                                                             | User logs in successfully                           | Medium   |
| RT_TC_13  | Retest cart total miscalculation                  | Add multiple products                                                        | Correct total shown                                 | Medium   |
| RT_TC_14  | Retest OTP resend button timing                   | Click resend OTP repeatedly                                                  | Delay or cooldown enforced                          | Medium   |
| RT_TC_15  | Retest product search                             | Enter keyword                                                                | Relevant results displayed                          | Medium   |

---

## regression

| TC ID     | Test Scenario                                      | Test Steps                                                                 | Expected Result                                      | Priority |
|-----------|---------------------------------------------------|------------------------------------------------------------------------------|-----------------------------------------------------|----------|
| RG_TC_01  | Ensure login works after password module update   | Login with valid credentials                                                | Login successful                                    | High     |
| RG_TC_02  | Check registration post database schema change    | Register new user                                                           | User registered successfully                        | High     |
| RG_TC_03  | Verify file upload after storage API change       | Upload file                                                                 | Upload successful                                   | High     |
| RG_TC_04  | Validate email sending post SMTP upgrade          | Send forgot password email                                                  | Email received                                      | High     |
| RG_TC_05  | Validate wishlist after UI update                 | Add product                                                                 | UI updates wishlist                                 | Medium   |
| RG_TC_06  | Validate cart persists after session enhancement  | Add items > Login/logout                                                    | Cart remains intact                                 | Medium   |
| RG_TC_07  | Check checkout after tax logic update             | Add items and checkout                                                      | Tax calculated correctly                            | High     |
| RG_TC_08  | Confirm sorting/filtering works                   | Apply price filter                                                          | Filtered list shown                                 | Medium   |
| RG_TC_09  | Ensure OTP verification after backend refactor    | Submit OTP                                                                  | Verification successful                             | High     |
| RG_TC_10  | Confirm search indexing works                     | Search product name                                                         | Accurate results                                    | Medium   |
| RG_TC_11  | Verify profile updates post patch release         | Change user name                                                            | Name updated                                        | Medium   |
| RG_TC_12  | Confirm dashboard data loads correctly            | Login and check stats                                                       | Correct info shown                                  | Medium   |
| RG_TC_13  | Check admin rights not lost post permission fix   | Login as admin                                                              | Admin functions visible                             | High     |
| RG_TC_14  | Confirm form submission after captcha integration | Fill and submit contact form                                                | Success message shown                               | Medium   |
| RG_TC_15  | Ensure mobile nav bar works                       | Open mobile site                                                            | Navigation opens/closes properly                    | Medium   |

---

## E2E 

| TC ID     | Test Scenario                                      | Test Steps                                                                 | Expected Result                                      | Priority |
|-----------|---------------------------------------------------|------------------------------------------------------------------------------|-----------------------------------------------------|----------|
| E2E_TC_01 | Complete user registration to login               | Register > Confirm email > Login                                            | User successfully onboarded                         | High     |
| E2E_TC_02 | User login and profile update                     | Login > Update profile > Save                                               | Data updated                                        | High     |
| E2E_TC_03 | Search and add product to cart                    | Search product > Add to cart                                                | Product added                                       | High     |
| E2E_TC_04 | Complete checkout with payment                    | Add to cart > Checkout > Pay                                                | Order placed                                        | High     |
| E2E_TC_05 | Password change and verification                  | Change password > Logout > Login                                            | New password works                                  | High     |
| E2E_TC_06 | Forgot password and reset                         | Request reset > Receive mail > Reset password                               | Password reset successful                           | High     |
| E2E_TC_07 | Social login to checkout                          | Login with Google > Add to cart > Checkout                                  | Order placed                                        | Medium   |
| E2E_TC_08 | File upload and download                          | Upload file > Download it                                                   | File downloads correctly                            | Medium   |
| E2E_TC_09 | Contact form submission and admin view            | Submit form > Login as admin > Check response                               | Form visible to admin                               | Medium   |
| E2E_TC_10 | View order history                                | Place order > Go to history                                                 | Order listed                                        | Medium   |
| E2E_TC_11 | OTP verification in login                         | Login with OTP                                                              | OTP verified and access granted                     | High     |
| E2E_TC_12 | Role switch and permission check                  | Login as admin > Edit user role > Verify permissions                        | User role changed and reflected                     | Medium   |
| E2E_TC_13 | Checkout cart with coupon                         | Add items > Apply coupon > Checkout                                         | Discount applied and order placed                   | Medium   |
| E2E_TC_14 | Pagination through order list                     | View multiple orders                                                        | Correct pagination works                            | Low      |
| E2E_TC_15 | Filtering products                                | Apply category filter                                                       | Filtered products shown                             | Medium   |
---
