# Forgot Password Test Cases

## Introduction

Forgot password testing ensures that users who have lost access to their credentials can securely and effectively reset their passwords. It validates that the process is functional, intuitive, and secure, without exposing sensitive data. Regression tests confirm system stability after changes, while boundary tests check how the system behaves at input and process limits.

---

## forgot_password_testcases
---
## positive

| TC ID   | Test Scenario                                         | Test Steps                                                                                      | Expected Result                                                                 | Priority |
|--------|--------------------------------------------------------|--------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|----------|
| TC_FP_P01 | Link visible on login page                            | Navigate to login page                                                                           | "Forgot Password" link should be clearly visible                               | High     |
| TC_FP_P02 | Redirection to reset page works                       | Click on "Forgot Password" link                                                                 | Redirects to password reset form                                               | High     |
| TC_FP_P03 | Valid email submission                                | Enter a registered email and click submit                                                       | Success message shown, reset email sent                                        | High     |
| TC_FP_P04 | Reset email received                                  | Complete request with valid email                                                               | Email with reset link/OTP received                                             | High     |
| TC_FP_P05 | OTP/link received quickly                             | Complete request and check email                                                                | Email/OTP received within acceptable time (e.g., under 2 mins)                 | Medium   |
| TC_FP_P06 | OTP/link is functional                                | Click on the reset link or enter OTP                                                            | Navigates to new password form                                                 | High     |
| TC_FP_P07 | Password reset with valid input                       | Enter strong new password and confirm                                                           | Password is successfully reset                                                 | High     |
| TC_FP_P08 | Login with new password                               | Use the newly reset password to log in                                                          | Login successful                                                               | High     |
| TC_FP_P09 | Password strength meter shown                         | Enter password in reset form                                                                    | Strength indicator appears and updates live                                    | Medium   |
| TC_FP_P10 | Form has client-side validations                      | Test with incorrect and correct inputs                                                          | Errors shown appropriately; validation works                                   | High     |
| TC_FP_P11 | Reset link single-use                                 | Use reset link once, then try again                                                             | Link works only once, shows expired if reused                                  | High     |
| TC_FP_P12 | Reset link expires after set time                     | Wait until expiration time and try link                                                         | Expired message shown                                                          | High     |
| TC_FP_P13 | User stays logged out during process                  | Start reset process without login                                                               | Session remains inactive                                                       | Medium   |
| TC_FP_P14 | Cancel button works                                   | Click cancel in reset form                                                                      | User redirected to login page                                                  | Low      |
| TC_FP_P15 | Accessible via keyboard and screen reader             | Navigate using Tab and screen reader                                                            | All fields and buttons are accessible                                          | Low      |


--------
## negative

| TC ID   | Test Scenario                                         | Test Steps                                                                                      | Expected Result                                                                 | Priority |
|--------|--------------------------------------------------------|--------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------|----------|
| TC_FP_N01 | Submit blank email                                     | Leave the email field empty and click submit                                                    | Error: "Email is required"                                                     | High     |
| TC_FP_N02 | Submit invalid email format                            | Enter "user.com" and submit                                                                     | Error: "Enter a valid email address"                                           | High     |
| TC_FP_N03 | Submit unregistered email                              | Enter an email not in the system                                                                | Error: "Email not found" or generic message                                    | Medium   |
| TC_FP_N04 | Use expired reset link                                 | Click on reset link after expiry                                                                | Error: "Link has expired"                                                      | High     |
| TC_FP_N05 | Use reset link multiple times                          | Click same link twice                                                                            | Error: "Link already used"                                                     | High     |
| TC_FP_N06 | Mismatched password and confirm password               | Enter different values in password fields                                                       | Error: "Passwords do not match"                                                | High     |
| TC_FP_N07 | Weak new password entry                                | Enter simple password like "12345"                                                              | Error: "Password too weak"                                                     | Medium   |
| TC_FP_N08 | Submit blank password                                  | Leave password blank                                                                            | Error: "Password is required"                                                  | High     |
| TC_FP_N09 | Submit blank confirm password                          | Leave confirm password blank                                                                    | Error: "Confirm password is required"                                          | High     |
| TC_FP_N10 | Tamper with reset link                                 | Modify link manually                                                                            | Error: "Invalid reset link"                                                    | High     |
| TC_FP_N11 | Submit form without internet                           | Disconnect network, fill and submit form                                                        | System shows "Network error" or fails to submit                                | Medium   |
| TC_FP_N12 | Email server down                                      | Submit valid email when email service is offline                                                | Email not received, and error (if applicable) logged or displayed              | Medium   |
| TC_FP_N13 | Autofill incorrect old email                           | Autofill browser-saved wrong email and submit                                                   | Password reset fails silently or error shown                                   | Low      |
| TC_FP_N14 | Error message not clearing after fix                   | Enter wrong email, fix it, re-submit                                                            | Old error message persists (this is a bug)                                     | Medium   |
| TC_FP_N15 | Form allows invalid characters                         | Enter script tags in email field (e.g., `<script>`)                                             | System should reject and sanitize input                                        | High     |

----------–-
## smoke

| TC ID     | Test Scenario                          | Test Steps                                                                   | Expected Result                                                  | Priority |
|-----------|-----------------------------------------|-------------------------------------------------------------------------------|------------------------------------------------------------------|----------|
| TC_SM_01  | Verify application launch                | Open the application in a supported browser                                  | Application homepage should load correctly                      | High     |
| TC_SM_02  | Login with valid credentials             | Enter valid email/password and login                                         | User should be redirected to the dashboard                      | High     |
| TC_SM_03  | Check logout functionality               | Click logout from dashboard                                                  | User should be redirected to login page                         | High     |
| TC_SM_04  | Forgot password workflow                 | Request reset with valid email                                               | Reset email/OTP should be received                              | Medium   |
| TC_SM_05  | Verify registration form loads           | Click "Sign Up" and open registration page                                   | Registration form loads properly                                | Medium   |
| TC_SM_06  | Dashboard loads post-login               | Login and observe dashboard                                                  | Dashboard should display user-specific data                     | High     |
| TC_SM_07  | Product search loads results             | Enter valid keyword in search and submit                                     | Results should be displayed                                     | Medium   |
| TC_SM_08  | Cart page opens                          | Click on Cart icon from navbar                                               | Cart page should display                                        | Medium   |
| TC_SM_09  | Add item to cart                         | Add a product to cart from product listing                                   | Cart item count increases                                       | High     |
| TC_SM_10  | Checkout page opens                      | Click “Checkout” from cart                                                   | Checkout page should be displayed                               | High     |
| TC_SM_11  | Payment page loads                       | Proceed to payment from checkout                                             | Payment gateway should appear                                   | High     |
| TC_SM_12  | Order confirmation                       | Complete payment                                                             | Confirmation page and order ID should be shown                  | High     |
| TC_SM_13  | Profile page loads                       | Navigate to user profile                                                     | Profile data is displayed                                       | Medium   |
| TC_SM_14  | Notifications display                    | Trigger action that shows notification                                       | Relevant notification is shown                                  | Low      |
| TC_SM_15  | Footer and header load correctly         | Visit multiple pages                                                         | Footer and header are consistent                                | Low      |


-----------–--
## sanity

| TC ID     | Test Scenario                          | Test Steps                                                                   | Expected Result                                                  | Priority |
|-----------|-----------------------------------------|-------------------------------------------------------------------------------|------------------------------------------------------------------|----------|
| TC_SA_01  | Login module                            | Test login with valid and invalid credentials                                | Login works correctly or error shown                            | High     |
| TC_SA_02  | Registration module                     | Fill registration form with all fields and submit                            | Account should be created                                       | High     |
| TC_SA_03  | Forgot password                         | Enter registered email and submit                                            | Reset email received                                             | High     |
| TC_SA_04  | Add to cart                             | Add item from product page                                                   | Item added to cart                                              | High     |
| TC_SA_05  | Remove from cart                        | Remove an item from cart                                                     | Cart updates correctly                                           | Medium   |
| TC_SA_06  | Place order                             | Add item > checkout > payment                                                | Order is placed successfully                                     | High     |
| TC_SA_07  | Profile update                          | Edit user profile info and save                                              | Changes saved                                                    | Medium   |
| TC_SA_08  | Password change                         | Update password from profile                                                 | Success message shown                                            | Medium   |
| TC_SA_09  | View order history                      | Go to order history page                                                     | Past orders shown                                                | Medium   |
| TC_SA_10  | Social login                            | Login with Google/Facebook                                                   | User logs in successfully                                        | Medium   |
| TC_SA_11  | Product filter                          | Apply brand/price filter                                                     | Results filtered properly                                        | Medium   |
| TC_SA_12  | Sorting                                 | Apply sorting to product list                                                | Results sorted accordingly                                       | Medium   |
| TC_SA_13  | Search                                  | Use search bar                                                               | Related results displayed                                        | Medium   |
| TC_SA_14  | File upload                             | Upload image in profile                                                      | File uploaded successfully                                       | Medium   |
| TC_SA_15  | Logout                                  | Click logout                                                                 | User session ends                                                | High     |

---------–-–--
## retesting

| TC ID     | Test Scenario                          | Test Steps                                                                   | Expected Result                                                  | Priority |
|-----------|-----------------------------------------|-------------------------------------------------------------------------------|------------------------------------------------------------------|----------|
| TC_RT_01  | Login with previously invalid password   | Retry with corrected password                                                | Login successful                                                 | High     |
| TC_RT_02  | Forgot password with valid email again   | Retry after initial failure                                                  | Reset mail received                                              | High     |
| TC_RT_03  | Registration with previously rejected data| Retry registration with fixed fields                                         | Registration succeeds                                            | High     |
| TC_RT_04  | Payment failed – retry with new card     | Attempt payment again                                                        | Payment successful                                               | High     |
| TC_RT_05  | Profile update not saved – retry         | Retry saving changes                                                         | Changes saved                                                    | Medium   |
| TC_RT_06  | Cart update failed – retry               | Add item to cart again                                                       | Item added                                                       | Medium   |
| TC_RT_07  | Order placement failed – retry           | Checkout again after failure                                                 | Order confirmed                                                  | High     |
| TC_RT_08  | File upload failed – retry               | Upload file again                                                            | Upload successful                                                | Medium   |
| TC_RT_09  | Invalid OTP – retry correct OTP          | Submit correct OTP after failure                                             | Success confirmation                                             | High     |
| TC_RT_10  | Change password failed – retry           | Reattempt with correct values                                                | Password updated                                                 | Medium   |
| TC_RT_11  | Social login failed – retry              | Retry Google/Facebook login                                                  | Login successful                                                 | Medium   |
| TC_RT_12  | Filter/sort not working – retry          | Apply filters again                                                          | Filters applied successfully                                     | Medium   |
| TC_RT_13  | Pagination failed – retry                | Navigate pages again                                                         | Pages load properly                                              | Medium   |
| TC_RT_14  | Email not received – re-request OTP      | Request OTP again                                                            | OTP received                                                     | High     |
| TC_RT_15  | Form submission failed – retry           | Resubmit feedback/contact form                                               | Form submitted successfully                                      | Medium   |

---

## Regression Test Cases

| TC ID      | Test Case Description                     | Test Steps                                        | Expected Result                        | Priority |
| ---------- | ----------------------------------------- | ------------------------------------------------- | -------------------------------------- | -------- |
| RP\_TC\_01 | Verify navigation to Forgot Password page | Click on 'Forgot Password' link from login screen | Forgot Password page is displayed      | High     |
| RP\_TC\_02 | Submit valid email for password reset     | Enter registered email and submit                 | Reset email sent successfully          | High     |
| RP\_TC\_03 | Submit unregistered email                 | Enter unregistered email and submit               | Appropriate error message displayed    | High     |
| RP\_TC\_04 | Submit empty email field                  | Leave email blank and submit                      | Validation error message shown         | Medium   |
| RP\_TC\_05 | Check reset link validity                 | Click the reset link received in email            | User redirected to reset password page | High     |
| RP\_TC\_06 | Check expired reset link                  | Use a link older than 24 hours                    | Expired link error message shown       | Medium   |
| RP\_TC\_07 | Password reset confirmation               | Enter new password and confirm                    | Password updated successfully          | High     |
| RP\_TC\_08 | Try reusing used reset link               | Use same link again                               | Link marked invalid or expired         | Medium   |
| RP\_TC\_09 | Verify login after reset                  | Login with new password                           | Login successful                       | High     |
| RP\_TC\_10 | Verify login fails with old password      | Attempt login with old password                   | Login fails with incorrect credentials | High     |

---


## Boundary Test Cases

| TC ID      | Test Case Description                     | Test Steps                                               | Expected Result                     | Priority |
| ---------- | ----------------------------------------- | -------------------------------------------------------- | ----------------------------------- | -------- |
| BP\_TC\_01 | Email field with max valid characters     | Enter 254-character email address                        | Accepted and processed              | Medium   |
| BP\_TC\_02 | Email field with 1 character before '@'   | Enter minimal valid email like [a@b.com](mailto:a@b.com) | Email accepted                      | Low      |
| BP\_TC\_03 | Email without '@' symbol                  | Enter string without @                                   | Error message shown                 | Medium   |
| BP\_TC\_04 | Email with special characters             | Enter email with allowed special characters              | Email accepted                      | Medium   |
| BP\_TC\_05 | Submit reset with leading/trailing spaces | Enter email with spaces                                  | Email trimmed and accepted          | Medium   |
| BP\_TC\_06 | Enter mismatched passwords                | Enter different passwords in reset form                  | Error shown                         | High     |
| BP\_TC\_07 | Submit reset with weak password           | Use '123' as new password                                | Weak password warning displayed     | Medium   |
| BP\_TC\_08 | Submit reset with long password           | Enter 100-character password                             | Password accepted (if limit allows) | Low      |
| BP\_TC\_09 | Submit reset with empty new password      | Leave password fields blank                              | Error message displayed             | High     |
| BP\_TC\_10 | Copy-paste same password in both fields   | Copy-paste matching passwords                            | Password successfully updated       | Medium   |

---


## e2e

| TC ID     | Test Scenario                          | Test Steps                                                                   | Expected Result                                                  | Priority |
|-----------|-----------------------------------------|-------------------------------------------------------------------------------|------------------------------------------------------------------|----------|
| TC_E2E_01 | User registration to login              | Register user → Logout → Login                                               | Full cycle works                                                 | High     |
| TC_E2E_02 | Login to order confirmation             | Login → Add item → Checkout → Confirm order                                  | Order placed successfully                                        | High     |
| TC_E2E_03 | Reset password full cycle               | Forgot password → Email → Reset → Login                                      | Password reset works end to end                                  | High     |
| TC_E2E_04 | Social login to profile update          | Login via Google → Update profile                                            | Flow works without issues                                        | Medium   |
| TC_E2E_05 | Guest to registered purchase            | Add item as guest → Register → Checkout                                      | Purchase successful                                               | High     |
| TC_E2E_06 | Search > view > add to cart > checkout  | Search product → View detail → Add to cart → Buy                             | End-to-end transaction completed                                 | High     |
| TC_E2E_07 | OTP verification during sign-up         | Register → Verify OTP → Login                                                | User signed up successfully                                      | High     |
| TC_E2E_08 | File upload > download                  | Upload document → Download same file                                         | Upload and download successful                                   | Medium   |
| TC_E2E_09 | Filter > sort > checkout                | Filter products → Sort → Select → Buy                                        | Flow works smoothly                                              | Medium   |
| TC_E2E_10 | Multi-device session check              | Login on one device → Perform actions → Check sync on another                | Data/session consistent                                          | Medium   |
| TC_E2E_11 | Contact form to email                   | Submit contact form → Check admin inbox                                      | Email received                                                    | Low      |
| TC_E2E_12 | Role-based navigation                   | Login as admin/user → Check accessible pages                                 | Role permissions respected                                       | High     |
| TC_E2E_13 | Add to wishlist → move to cart → buy    | Add to wishlist → Move to cart → Buy                                         | Product bought successfully                                      | Medium   |
| TC_E2E_14 | Email verification post-registration    | Register → Check inbox → Verify email                                        | Email verified                                                    | High     |
| TC_E2E_15 | Infinite scroll till checkout           | Scroll products → Add item from bottom → Checkout                            | Checkout works seamlessly                                        | Medium   |

---


**Prepared by:** [Pratik Joshi]   
**Module:** | Form Testing | forgot-password-testcases |
