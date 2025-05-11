# Form Testing - Detailed Test Cases

This document contains 50 detailed test cases for validating form functionalities commonly found in web and mobile applications. The test cases cover a broad spectrum of aspects such as field validation, UI/UX behavior, functional correctness, error handling, security, and responsive design. These test cases can be applied to various types of forms, including registration, contact, feedback, and data entry forms.

Each test case includes the test scenario, detailed test steps, sample test data, expected outcome, and priority level to help in planning and execution during different testing phases such as sanity, smoke, regression, and end-to-end testing.

### Goals of These Test Cases:

- Ensure all fields and form behaviors work correctly under various input conditions.
- Verify both client-side and server-side validation.
- Validate user experience elements like error messages, form layout, accessibility, and responsiveness.
- Test for edge cases, security vulnerabilities (e.g., SQL Injection, XSS), and usability issues.

Use these test cases to create a strong foundation for your QA portfolio, test documentation, or automation coverage.

| **TC ID** | **Test Scenario**                                    | **Test Steps**                                                     | **Test Data**                        | **Expected Result**                                      | **Priority** |
|-----------|-------------------------------------------------------|--------------------------------------------------------------------|--------------------------------------|----------------------------------------------------------|--------------|
| TC001     | Check form loads correctly                           | Navigate to the form page                                          | N/A                                  | Form should be displayed properly                         | High         |
| TC002     | Validate all mandatory fields                        | Try submitting the form with mandatory fields empty                | Leave all required fields blank      | Error messages should appear for required fields          | High         |
| TC003     | Validate successful form submission                  | Fill all fields correctly and submit the form                      | Valid user input                     | Form should be submitted successfully                     | High         |
| TC004     | Validate email field with invalid input              | Enter invalid email format and submit                              | “userexample.com”                    | Error message: “Invalid email address”                   | High         |
| TC005     | Validate email field with valid input                | Enter valid email format                                           | “user@example.com”                   | Email accepted without error                              | Medium       |
| TC006     | Validate numeric-only fields                         | Enter alphabets in numeric field                                   | “abcd”                               | Show validation error                                     | High         |
| TC007     | Validate special characters in name fields           | Enter special characters in name fields                            | “@#$$%”                              | Show validation error                                     | Medium       |
| TC008     | Check maximum character limit in text field          | Input exceeds maximum limit                                        | 300 characters in 255-char field     | Error or text should be trimmed                           | Medium       |
| TC009     | Check minimum character limit in text field          | Input below minimum limit                                          | 1 character in 5-min field           | Show validation error                                     | Medium       |
| TC010     | Validate form reset functionality                    | Fill in data, then click Reset/Cancel                              | Any input                            | All fields should be cleared                               | Low          |
| TC011     | Validate drop-down selection                         | Select an option from dropdown                                     | Choose “Option 2”                    | Option should be selected and submitted                    | Medium       |
| TC012     | Check default values in fields                       | Load form                                                          | N/A                                  | Default values (if any) should be present                 | Low          |
| TC013     | Validate radio button selection                      | Select one option from radio buttons                               | Select “Male”                        | Only one option should be selected                         | Medium       |
| TC014     | Validate checkbox multiple selections                | Select multiple checkboxes                                         | Select “Option A”, “Option B”        | Multiple selections should be allowed                      | Medium       |
| TC015     | Check submission without checkbox checked            | Leave agreement checkbox unchecked and submit                      | N/A                                  | Error: “Please accept terms and conditions”               | High         |
| TC016     | Validate file upload field                           | Try uploading a file                                               | .pdf, .doc, .jpg                     | Accept or reject based on allowed file types              | Medium       |
| TC017     | Validate large file upload                           | Upload file larger than max size                                   | 10MB file if 5MB allowed             | Show size exceeded error                                   | Medium       |
| TC018     | Validate password masking                            | Enter password in field                                            | “Password123”                        | Input should be hidden (dots or asterisks)                | Medium       |
| TC019     | Check password confirmation match                    | Enter different passwords                                          | “Pass123”, “Pass124”                 | Show error: “Passwords do not match”                      | High         |
| TC020     | Check autocomplete off                               | Start typing in form fields                                        | Input “abc”                          | Autocomplete should be disabled                           | Low          |
| TC021     | Validate placeholder text                            | View fields without entering anything                              | N/A                                  | Placeholder should provide guidance                       | Low          |
| TC022     | Validate date field                                  | Enter/select invalid date                                          | 31-Feb-2023                           | Show validation error                                     | Medium       |
| TC023     | Check required format for phone number               | Enter phone number in incorrect format                             | “1234abc”                            | Show format error                                         | High         |
| TC024     | Validate spacing before/after input                  | Add leading/trailing spaces                                        | “ John ”                             | Trim spaces before validation                             | Medium       |
| TC025     | Check for SQL injection                              | Input SQL script in text fields                                    | “’; DROP TABLE users;”               | Input should be sanitized                                 | High         |
| TC026     | Check for XSS attack                                 | Input script tags in fields                                        | “”                                   | Show as plain text or block input                         | High         |
| TC027     | Test form submission multiple times                  | Click submit button repeatedly                                     | Valid data                           | Should submit once or prevent double submission            | Medium       |
| TC028     | Check response time after form submission            | Submit form                                                        | Valid data                           | Should respond within 3 seconds                            | Medium       |
| TC029     | Validate form behavior on browser refresh            | Fill form and refresh                                              | Filled form                          | Data may reset or prompt user before refresh               | Low          |
| TC030     | Check behavior on back button after submit           | Submit form, click browser back                                    | N/A                                  | Should not resubmit form on back                          | Medium       |
| TC031     | Validate multiline text area                         | Enter multiple lines of text                                       | Paragraphs                           | Should retain formatting                                  | Low          |
| TC032     | Test keyboard navigation                             | Use Tab/Shift+Tab to navigate fields                               | N/A                                  | Should move focus in logical order                        | Medium       |
| TC033     | Test mobile responsiveness                           | Open form on mobile device                                         | N/A                                  | Should display properly, no horizontal scroll              | High         |
| TC034     | Validate on-screen keyboard support                  | Use on-screen keyboard (touch devices)                             | N/A                                  | Inputs should accept characters                           | Low          |
| TC035     | Validate language localization                       | Switch to another language                                         | Choose “Spanish”                     | Labels should translate                                   | Low          |
| TC036     | Validate time field input                            | Enter invalid time                                                 | “25:00”                              | Show error: invalid time                                  | Medium       |
| TC037     | Validate CAPTCHA integration                         | Try submitting form with wrong CAPTCHA                             | Incorrect CAPTCHA                    | Should not submit                                           | High         |
| TC038     | Test disabled field                                  | Try to edit or select disabled fields                              | N/A                                  | Should not allow interaction                               | Medium       |
| TC039     | Check tooltip/help text on hover                     | Hover over info icon                                               | N/A                                  | Tooltip/help text should appear                           | Low          |
| TC040     | Validate session timeout                             | Keep form idle for long time and submit                            | N/A                                  | Should expire or show timeout message                     | Medium       |
| TC041     | Validate confirmation message after submit           | Submit valid form                                                  | Valid data                           | Show “Thank you” or confirmation                          | Medium       |
| TC042     | Validate required field asterisk                     | View form                                                          | N/A                                  | Required fields should be marked with *                   | Low          |
| TC043     | Validate accessibility with screen reader            | Use screen reader to read form                                     | N/A                                  | Labels and fields should be accessible                     | Medium       |
| TC044     | Validate auto-tab to next field                      | Enter max characters in field                                      | 10-digit phone number                | Cursor moves to next field automatically                  | Low          |
| TC045     | Test submission without internet                     | Disconnect internet and submit                                     | Valid input                          | Show network error or retry option                        | Medium       |
| TC046     | Validate country and state dependency                | Select country, check if states load                               | Select “USA”                         | State dropdown updates accordingly                        | Medium       |
| TC047     | Validate date picker default value                   | Open date picker                                                   | N/A                                  | Default to today’s date or blank                          | Low          |
| TC048     | Validate multiline special characters                 | Paste text with special characters                                | “!@#%$^&*()”                          | Should not break layout                                   | Medium       |
| TC049     | Validate dynamic form field visibility               | Trigger field visibility (e.g. toggle “Other”)                    | Select “Other”                       | Related input field appears                               | Medium       |
| TC050     | Test form submission in multiple tabs                | Open same form in multiple tabs                                    | Submit from both                     | Should prevent duplicates                                 | Medium       |

## Conclusion

The above 50 test cases provide comprehensive coverage of the critical aspects involved in form validation and behavior testing. By systematically executing these cases, testers can ensure that the form is reliable, secure, user-friendly, and robust against both typical and edge-case inputs.

This document can serve as a reusable checklist for manual testing, a reference for creating automated test scripts, or as part of a QA portfolio to showcase a detailed understanding of form-based UI testing.

For further enhancements, consider:
- Adding browser-specific form behavior test cases
- Expanding with negative testing scenarios
- Including API-level validation if the form is integrated with backend services

Prepared by: [Pratik Joshi]  
Project/Module: Form Functionality Testing
