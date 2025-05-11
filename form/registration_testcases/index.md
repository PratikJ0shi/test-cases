# Registration Functionality - Test Cases (20 Total)

> These test cases focus on the **functional behavior** of the registration page.

---
## registration_testcases

| TC ID     | Title                                      | Steps                                                                 | Expected Result                                      |
|-----------|--------------------------------------------|-----------------------------------------------------------------------|------------------------------------------------------|
| REG_01    | Valid registration                         | Fill all valid fields → Submit                                       | Account created successfully                         |
| REG_02    | Required fields validation                 | Leave all fields empty → Submit                                      | "Required field" errors shown for each field         |
| REG_03    | Email format validation                    | Enter `user@com` or `user@.com` → Submit                             | "Invalid email format" error                         |
| REG_04    | Password strength enforcement              | Enter weak password → Submit                                         | "Password too weak" error shown                      |
| REG_05    | Confirm password match check               | Enter mismatching confirm password → Submit                          | "Passwords do not match" error                       |
| REG_06    | Email uniqueness check                     | Enter already registered email                                       | "Email already exists" error                         |
| REG_07    | Phone number validation                    | Enter letters in phone field → Submit                                | "Invalid phone number" error                         |
| REG_08    | Field length validations                   | Enter over 255 chars in fields → Submit                              | Field is truncated or error shown                    |
| REG_09    | Terms & Conditions checkbox unchecked      | Leave checkbox unchecked → Submit                                    | Warning shown: must agree to terms                   |
| REG_10    | Successful redirection post-registration   | Complete form → Submit                                               | Redirects to login or dashboard                      |
| REG_11    | Country dropdown populated                 | Open registration page                                               | Country list is populated                           |
| REG_12    | Password input masked                      | Type in password field                                               | Input is hidden (masked with dots or asterisks)      |
| REG_13    | Clear form after success                   | Register successfully                                                | Form fields are cleared/reset                        |
| REG_14    | Mobile number length check                 | Enter <10 or >10 digits                                              | Error shown for invalid length                       |
| REG_15    | Auto-format email on blur                  | Enter space in email → Click outside                                | Trims spaces automatically                           |
| REG_16    | Show/hide password toggle                  | Click eye icon on password field                                     | Password visibility toggles                          |
| REG_17    | Resubmission prevention                    | Submit form twice quickly                                            | Only one registration request is processed           |
| REG_18    | Duplicate phone number check               | Enter registered phone → Submit                                      | Error: "Phone number already exists"                 |
| REG_19    | Email confirmation (if applicable)         | Submit form                                                          | Verification email sent                              |
| REG_20    | All labels and placeholders visible        | Open registration form                                               | Labels and placeholders match field functionality    |

---

## Notes:
- Make sure your UI validates both client-side and server-side.
- Most of these cases are useful for both manual and automated testing.

# User Registration Test Cases (Functional)

This document includes 40 test cases — **20 Positive** and **20 Negative** — for the user registration form with clear metadata.

---

## positive

| Test ID | Title                            | Precondition                        | Steps                                                             | Expected Result                           | Priority |
|---------|----------------------------------|-------------------------------------|-------------------------------------------------------------------|-------------------------------------------|----------|
| POS_01  | Valid registration               | Registration page loaded            | Enter valid inputs → Submit                                       | Account created, redirected to login      | High     |
| POS_02  | Strong password accepted         | Registration page loaded            | Enter complex password                                            | Accepted                                  | High     |
| POS_03  | Confirm password match           | Registration page loaded            | Match confirm password                                            | Accepted                                  | High     |
| POS_04  | Valid email format               | Registration page loaded            | Enter `user@example.com`                                          | Accepted                                  | High     |
| POS_05  | Valid mobile number              | Registration page loaded            | Enter 10-digit phone number                                       | Accepted                                  | High     |
| POS_06  | Redirect to login on success     | Form submitted                      | Submit valid form                                                 | Redirects to login                         | High     |
| POS_07  | Gender dropdown working          | Registration page loaded            | Select any gender                                                 | Selection retained                         | Medium   |
| POS_08  | Country dropdown populated       | Registration page loaded            | Open country dropdown                                             | Shows all countries                        | Medium   |
| POS_09  | Terms checkbox works             | Registration page loaded            | Check the checkbox → Submit                                       | Registration successful                    | High     |
| POS_10  | Input trimming                   | Registration page loaded            | Add spaces to email → Submit                                      | Spaces trimmed, valid submission           | Medium   |
| POS_11  | Show/hide password icon          | Registration page loaded            | Toggle password visibility                                        | Password appears/disappears                | Low      |
| POS_12  | Tab key navigation               | Registration page loaded            | Use Tab to move fields                                            | Focus changes in logical order             | Low      |
| POS_13  | Field labels visible             | Registration page loaded            | Check all field labels                                            | Labels present and readable                | Medium   |
| POS_14  | Placeholder text guides user     | Registration page loaded            | Check placeholders                                                | Guidance shown                             | Low      |
| POS_15  | Form submission via Enter key    | All fields filled                   | Press Enter                                                       | Form submits                               | Medium   |
| POS_16  | Mobile responsive layout         | Open on mobile                      | View form                                                         | Responsive layout                          | Medium   |
| POS_17  | No duplication on refresh        | Submit form → Refresh page          | Refresh browser                                                   | No duplicate account                       | High     |
| POS_18  | Confirmation email triggered     | Registration page loaded            | Register new account                                              | Email sent                                 | Medium   |
| POS_19  | Browser autofill supported       | Autofill enabled in browser         | Autofill details                                                  | Fields fill correctly                      | Low      |
| POS_20  | Password field is masked         | Registration page loaded            | Enter password                                                    | Characters masked                          | High     |

---

## negative

| Test ID | Title                            | Precondition                        | Steps                                                             | Expected Result                           | Priority |
|---------|----------------------------------|-------------------------------------|-------------------------------------------------------------------|-------------------------------------------|----------|
| NEG_01  | Submit empty form                | Registration page loaded            | Submit without input                                              | All fields show error                      | High     |
| NEG_02  | Invalid email format             | Registration page loaded            | Enter `user@com` → Submit                                         | Email format error                         | High     |
| NEG_03  | Weak password                    | Registration page loaded            | Enter "123" → Submit                                              | Password strength error                    | High     |
| NEG_04  | Passwords mismatch               | Registration page loaded            | Enter mismatching passwords                                       | Validation error                           | High     |
| NEG_05  | Duplicate email used             | Email already registered            | Enter registered email                                            | "Email already exists" error               | High     |
| NEG_06  | Duplicate phone number           | Phone number already registered     | Enter same phone number                                           | "Phone already exists" error               | High     |
| NEG_07  | Terms checkbox unchecked         | Registration page loaded            | Submit without checking checkbox                                  | Error shown                                | Medium   |
| NEG_08  | Less than 10-digit phone         | Registration page loaded            | Enter 7-digit number                                              | Phone format error                         | High     |
| NEG_09  | More than 10-digit phone         | Registration page loaded            | Enter 15-digit number                                             | Phone format error                         | High     |
| NEG_10  | Special characters in name       | Registration page loaded            | Enter `@@@###` in name                                            | Name validation error                      | Medium   |
| NEG_11  | XSS input in name                | Registration page loaded            | Enter `<script>` in name                                          | Rejected or escaped                        | High     |
| NEG_12  | SQL injection in email           | Registration page loaded            | Input `' OR 1=1 --` in email                                      | Validation/rejection                       | High     |
| NEG_13  | Password is only spaces          | Registration page loaded            | Enter `"     "` in password                                       | Error shown                                | Medium   |
| NEG_14  | HTML tags in fields              | Registration page loaded            | Input `<div>` in name/email                                       | Sanitized or error                         | Medium   |
| NEG_15  | Expired session submission       | Idle for long → Submit              | Form submission after session timeout                             | "Session expired" error                    | Medium   |
| NEG_16  | Double-click register            | Click register rapidly              | Multiple clicks on register                                       | Only one user created                      | High     |
| NEG_17  | Fields exceed max length         | Registration page loaded            | Enter 1000+ chars in name/email                                   | Field blocks input or error shown          | Medium   |
| NEG_18  | Emoji input in name              | Registration page loaded            | Enter emoji                                                       | Rejected or accepted based on spec         | Low      |
| NEG_19  | Confirm password empty           | Registration page loaded            | Leave confirm password blank                                      | Required field error                       | High     |
| NEG_20  | Bypass disabled fields           | Modify fields via browser tools     | Submit tampered field                                             | Server ignores invalid field               | High     |

---
# Registration Test Cases Documentation

## sanity
Sanity testing is used to quickly evaluate if the basic functionality works and there are no critical errors in the registration process.

| Test Case No. | Test Case Description                                              | Precondition                         | Test Steps                                                                                                      | Expected Result                                                  |
|---------------|--------------------------------------------------------------------|--------------------------------------|-----------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| 1             | Verify registration page loads correctly                           | None                                 | 1. Navigate to the registration page URL.                                                                        | Page should load without errors.                                |
| 2             | Verify presence of mandatory fields                               | Registration page is loaded          | 1. Check that fields such as Name, Email, Password, Confirm Password are present.                               | Mandatory fields should be present.                             |
| 3             | Verify successful form submission with valid data                 | All required fields are filled       | 1. Enter valid data in all required fields. <br> 2. Click 'Submit'.                                              | Registration should be successful and user should be redirected.|
| 4             | Verify invalid email format handling                              | Email field is visible               | 1. Enter an invalid email (e.g., "invalid.com"). <br> 2. Click 'Submit'.                                        | Error message should show for invalid email.                   |
| 5             | Verify password mismatch warning                                  | Password and Confirm Password fields | 1. Enter mismatched passwords in the Password and Confirm Password fields. <br> 2. Click 'Submit'.              | Password mismatch error message should appear.                 |
| 6             | Verify email field accepts only valid emails                      | Email field is present               | 1. Enter valid email format (e.g., "user@example.com"). <br> 2. Submit the form.                               | Email should be accepted without error.                         |
| 7             | Verify that password field accepts secure passwords               | Password field is visible            | 1. Enter a secure password (e.g., "Password@123"). <br> 2. Submit the form.                                     | Password should be accepted if secure.                         |
| 8             | Verify that password field does not accept insecure passwords     | Password field is visible            | 1. Enter an insecure password (e.g., "password"). <br> 2. Submit the form.                                     | Error message should appear for insecure password.             |
| 9             | Verify form reset functionality                                   | Registration form is visible         | 1. Fill in data in some fields. <br> 2. Click 'Reset'.                                                           | All fields should be cleared.                                   |
| 10            | Verify email field does not accept empty values                   | Email field is visible               | 1. Leave the email field empty. <br> 2. Submit the form.                                                        | Error message should show for empty email field.               |
| 11            | Verify that the registration page is responsive                   | None                                 | 1. Open the registration page on different devices (desktop, tablet, mobile).                                  | Page should be responsive across devices.                      |
| 12            | Verify the presence of 'Submit' and 'Cancel' buttons               | Registration page is loaded          | 1. Check if the 'Submit' and 'Cancel' buttons are visible and functional.                                        | Both buttons should be visible and functional.                 |
| 13            | Verify user is redirected to the confirmation page                | Registration form is successfully submitted | 1. Submit the form with valid data. <br> 2. Verify the system redirects to a confirmation or success page.       | User should be redirected to confirmation page.                |
| 14            | Verify password confirmation field works                          | Password and Confirm Password fields | 1. Enter matching passwords in both fields. <br> 2. Submit the form.                                            | Password should be confirmed and form should submit successfully.|
| 15            | Verify registration page is accessible via URL                    | None                                 | 1. Enter the registration page URL in the browser.                                                              | Page should be accessible without errors.                      |

---

## retesting
Retesting focuses on verifying that a defect has been fixed in the system, confirming the same defect no longer occurs.

| Test Case No. | Test Case Description                                             | Precondition                         | Test Steps                                                                                                      | Expected Result                                                  |
|---------------|-------------------------------------------------------------------|--------------------------------------|-----------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| 1             | Verify defect fix for form submission                            | A defect in form submission was fixed | 1. Fill out the registration form with valid data. <br> 2. Submit the form.                                    | Form should submit successfully without errors.                 |
| 2             | Verify password mismatch error handling after bug fix            | A defect related to password mismatch was fixed | 1. Enter mismatched passwords in the Password and Confirm Password fields. <br> 2. Submit the form.              | Error message should show for password mismatch.                 |
| 3             | Verify email validation after bug fix                            | A bug related to email validation was fixed | 1. Enter an invalid email (e.g., "invalid.com"). <br> 2. Submit the form.                                        | Error message should show for invalid email format.             |
| 4             | Verify user registration and email verification after fix        | Email verification bug was fixed     | 1. Complete registration and check if an email verification link is sent.                                        | Email verification should be sent correctly.                    |
| 5             | Verify reset functionality works after defect fix                | A defect in form reset functionality was fixed | 1. Fill the form with random data. <br> 2. Click 'Reset'.                                                         | All fields should be cleared after clicking 'Reset'.            |
| 6             | Verify form submission is successful after defect fix            | Previous defect was fixed            | 1. Fill out all required fields with valid data. <br> 2. Click 'Submit'.                                        | Form should submit successfully.                                 |
| 7             | Verify field validation works after fix                           | Validation defects were fixed        | 1. Leave one or more required fields empty. <br> 2. Submit the form.                                            | Error message should appear for missing required fields.         |
| 8             | Verify successful redirection to confirmation page after fix     | A bug related to page redirection was fixed | 1. Complete the registration form. <br> 2. Submit the form.                                                     | User should be redirected to the confirmation page.             |
| 9             | Verify successful login after registration bug fix               | Registration system was fixed        | 1. Complete registration with valid data. <br> 2. Log in using the newly created credentials.                   | Login should be successful with new credentials.                |
| 10            | Verify page responsiveness after bug fix                         | A responsiveness bug was fixed       | 1. Open the registration page on different devices (desktop, tablet, mobile).                                  | Page should be responsive across devices.                      |
| 11            | Verify form field tooltips work after defect fix                 | Tooltips were not working earlier    | 1. Hover over fields like Name, Email, Password, and Confirm Password.                                          | Tooltips should appear for each field.                          |
| 12            | Verify 'Submit' button functionality after defect fix            | A defect with 'Submit' button was fixed | 1. Fill out the form. <br> 2. Click 'Submit'.                                                                  | 'Submit' button should work without any error.                 |
| 13            | Verify form data saving works after fix                          | A bug related to data saving was fixed | 1. Enter data in the registration form. <br> 2. Submit the form. <br> 3. Verify that the data is saved in the database. | Data should be saved correctly after submission.                |
| 14            | Verify no crash happens on form submission after fix             | Previous crash bug was fixed         | 1. Fill out the registration form. <br> 2. Click 'Submit'.                                                      | No crash should occur on form submission.                       |
| 15            | Verify cancel functionality works after defect fix               | Cancel button was broken earlier     | 1. Fill in some details in the registration form. <br> 2. Click 'Cancel'.                                       | All form data should be cleared and user redirected properly.   |

---

## regression
Regression testing ensures that the system still functions as expected after updates or fixes.

| Test Case No. | Test Case Description                                             | Precondition                         | Test Steps                                                                                                      | Expected Result                                                  |
|---------------|-------------------------------------------------------------------|--------------------------------------|-----------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| 1             | Verify login functionality works after registration system update | Login functionality is operational  | 1. Complete the registration process. <br> 2. Log in using the newly created credentials.                        | Login should be successful for the newly registered user.      |
| 2             | Verify previous user data is not affected by registration update  | System has existing users            | 1. Register a new user. <br> 2. Verify that pre-existing users are still functional and able to log in.         | Existing users should still be able to log in.                   |
| 3             | Verify data integrity after registration update                   | Data integrity is crucial            | 1. Complete the registration process. <br> 2. Verify that the data entered (email, password, etc.) is correct.  | Data should be correctly saved and displayed in the database.   |
| 4             | Verify successful form submission after update                    | Form submission functionality is fixed | 1. Complete the form with valid data. <br> 2. Submit the form.                                                  | Form should submit successfully without errors.                 |
| 5             | Verify confirmation page is displayed after registration update   | Registration process is complete      | 1. Complete the registration form. <br> 2. Submit the form. <br> 3. Verify that the user is redirected to the confirmation page. | User should be redirected to the confirmation page.             |
| 6             | Verify form field validation after system update                  | Validation mechanism is fixed         | 1. Leave a required field empty (e.g., email). <br> 2. Submit the form.                                        | Error message should appear for the empty field.               |
| 7             | Verify registration page is accessible across different devices  | None                                 | 1. Open the registration page on multiple devices (desktop, tablet, mobile).                                     | Page should be responsive across devices.                      |
| 8             | Verify the page does not crash after form submission              | Form submission functionality is fixed | 1. Complete the form with valid data. <br> 2. Submit the form.                                                  | No crash should occur after submitting the form.                |
| 9             | Verify the presence of required fields after updates              | Fields are defined                    | 1. Open the registration page. <br> 2. Ensure that required fields like Name, Email, Password, and Confirm Password are visible. | All required fields should be visible.                          |
| 10            | Verify that the 'Cancel' button works                            | None                                 | 1. Enter data into the registration form. <br> 2. Click 'Cancel'.                                               | Form should be reset and user should be taken to the previous page. |
| 11            | Verify that the error messages display correctly after updates    | Error handling mechanism is updated   | 1. Enter invalid data (e.g., wrong email). <br> 2. Submit the form.                                              | Correct error messages should appear.                           |
| 12            | Verify registration system works for multiple users simultaneously | None                                 | 1. Simultaneously submit two registration forms with different data.                                             | Both users should be registered successfully.                  |
| 13            | Verify form field tooltips work correctly                        | Tooltips should be displayed         | 1. Hover over fields like Name, Email, Password.                                                                 | Tooltips should appear for all fields.                         |
| 14            | Verify the functionality of 'Submit' and 'Reset' buttons         | Buttons should work                   | 1. Fill the form and click 'Submit'. <br> 2. Check that the form submits successfully. <br> 3. Test the 'Reset' button. | Both buttons should work as expected.                          |
| 15            | Verify user data is displayed correctly in confirmation page    | None                                 | 1. Complete the registration process. <br> 2. Verify that the data entered in the form is displayed correctly on the confirmation page. | User data should be displayed accurately.                      |


---

## smoke
Smoke testing ensures that basic functionalities are working before more extensive testing is done.

| Test Case No. | Test Case Description                                              | Precondition                         | Test Steps                                                                                                      | Expected Result                                                  |
|---------------|--------------------------------------------------------------------|--------------------------------------|-----------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| 1             | Verify registration page loads correctly                           | None                                 | 1. Navigate to the registration page URL.                                                                        | Page should load without errors.                                |
| 2             | Verify presence of mandatory fields                               | Registration page is loaded          | 1. Check that fields such as Name, Email, Password, Confirm Password are present.                               | Mandatory fields should be present.                             |
| 3             | Verify successful form submission with valid data                 | All required fields are filled       | 1. Enter valid data in all required fields. <br> 2. Click 'Submit'.                                              | Registration should be successful and user should be redirected.|
| 4             | Verify invalid email format handling                              | Email field is visible               | 1. Enter an invalid email (e.g., "invalid.com"). <br> 2. Click 'Submit'.                                        | Error message should show for invalid email.                   |
| 5             | Verify password mismatch warning                                  | Password and Confirm Password fields | 1. Enter mismatched passwords in the Password and Confirm Password fields. <br> 2. Click 'Submit'.              | Password mismatch error message should appear.                 |
| 6             | Verify reset functionality works                                  | None                                 | 1. Fill out data in some fields. <br> 2. Click 'Reset'.                                                           | All fields should be cleared.                                   |
| 7             | Verify the form fields are reset when 'Cancel' is clicked          | None                                 | 1. Enter some data. <br> 2. Click the 'Cancel' button.                                                           | Fields should be cleared and form should be reset.              |
| 8             | Verify that the form does not submit with missing required fields | Required fields are left empty       | 1. Leave required fields empty (e.g., Name or Email). <br> 2. Click 'Submit'.                                    | Error message should show for missing required fields.         |
| 9             | Verify the 'Submit' button functionality                           | Form is filled with valid data       | 1. Complete all fields with valid data. <br> 2. Click 'Submit'.                                                 | Form should submit successfully.                                 |
| 10            | Verify successful registration after entering valid credentials   | Valid data is entered                | 1. Enter valid credentials (e.g., Name, Email, Password). <br> 2. Click 'Submit'.                               | User should be successfully registered.                         |
| 11            | Verify page is responsive on different devices                     | None                                 | 1. Open the registration page on different devices (desktop, tablet, mobile).                                  | Page should be responsive across devices.                      |
| 12            | Verify user redirection to success page after registration        | Registration is successful           | 1. Complete the registration form. <br> 2. Submit the form. <br> 3. Check if the user is redirected to a confirmation page. | User should be redirected to confirmation page.                 |
| 13            | Verify error messages for incorrect input                          | Invalid data is entered              | 1. Enter invalid input (e.g., empty fields, incorrect email format). <br> 2. Submit the form.                   | Error message should be displayed for incorrect input.         |
| 14            | Verify all form fields are accessible and interactable            | None                                 | 1. Open the registration form and check if all fields are accessible (Name, Email, Password).                   | All fields should be accessible.                                |
| 15            | Verify that the system does not crash during form submission      | None                                 | 1. Fill the form with valid data. <br> 2. Submit the form.                                                      | No system crash should occur during form submission.            |

---

## e2e
End-to-End testing ensures that the entire registration process works as expected from start to finish.

| Test Case No. | Test Case Description                                             | Precondition                         | Test Steps                                                                                                      | Expected Result                                                  |
|---------------|-------------------------------------------------------------------|--------------------------------------|-----------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------|
| 1             | Verify complete registration process                             | None                                 | 1. Fill the registration form with valid data. <br> 2. Submit the form. <br> 3. Verify confirmation page.        | User should be successfully registered and redirected.          |
| 2             | Verify registration, email verification, and login               | Email verification is enabled        | 1. Complete registration. <br> 2. Verify email verification link is received. <br> 3. Log in with the credentials. | User should be able to verify the email and log in.             |
| 3             | Verify that the user is not registered if mandatory fields are missing | None                             | 1. Leave one or more required fields empty. <br> 2. Submit the form.                                            | Form should not submit and error should be displayed.            |
| 4             | Verify cancel functionality during the registration process      | None                                 | 1. Enter data into the form. <br> 2. Click 'Cancel'.                                                             | Form data should be cleared and user redirected.                |
| 5             | Verify successful registration and confirmation email            | None                                 | 1. Fill in valid registration data. <br> 2. Submit the form. <br> 3. Check the email inbox for confirmation.    | User should receive a confirmation email.                       |

---
**Prepared by:** [Pratik Joshi]   
**Module:** | Form Testing | registration-testcases |
