# 🧾 User Profile Module - UI & Functional Test Suite

## Overview

This document outlines the comprehensive set of test cases for the **User Profile** module of a web application. The module enables users to view, update, and manage their personal information such as name, email, password, profile picture, and preferences.

The test suite is divided into two main categories:

- **UI Test Cases** – These focus on verifying the visual presentation and responsiveness of UI elements such as input fields, labels, buttons, and layout across various screen sizes.
- **Functional Test Cases** – These validate the underlying functionality of profile-related features including data updates, validations, file uploads, password changes, and session behavior.

Each test case includes a unique ID, description, step-by-step actions, expected result, and priority to aid in planning and execution.

> **Purpose:** Ensure the profile section of the application delivers a seamless, intuitive, and error-free user experience across both user interface and functional aspects.


## User Profile - UI Test Cases

| TC ID      | Test Case Description                                      | Test Steps                                                                 | Expected Result                                                  | Priority |
|------------|------------------------------------------------------------|-----------------------------------------------------------------------------|------------------------------------------------------------------|----------|
| UI_TC_01   | Verify profile picture is visible                          | Navigate to profile page                                                   | Profile picture should be displayed                              | High     |
| UI_TC_02   | Validate profile page layout                               | Open profile page                                                          | Page layout should follow design specs                           | Medium   |
| UI_TC_03   | Check label alignment                                      | Verify labels (e.g., Name, Email) are properly aligned                     | All labels should be left-aligned consistently                   | Medium   |
| UI_TC_04   | Check input fields styling                                 | Inspect input fields for border, padding, font                            | All fields should follow standard styling                        | Medium   |
| UI_TC_05   | Verify edit icons are visible                              | Look for edit icons next to editable fields                               | Edit icons should be visible                                     | High     |
| UI_TC_06   | Confirm responsive layout                                  | Open on different screen sizes (mobile, tablet, desktop)                  | Layout should adjust properly                                    | High     |
| UI_TC_07   | Validate save/cancel button styling                        | Check buttons at bottom of form                                           | Buttons should be clearly distinguishable                        | Medium   |
| UI_TC_08   | Check error message visibility                             | Enter invalid data                                                         | Error message should be visible and styled consistently          | High     |
| UI_TC_09   | Verify font consistency                                    | Review all text on profile page                                            | Font family, size, and weight should match spec                  | Medium   |
| UI_TC_10   | Ensure profile sections are separated clearly              | Observe section headers and spacing                                        | Sections should be visually distinct                             | Low      |
| UI_TC_11   | Validate dropdown styling (e.g., gender, country)          | Open dropdown fields                                                       | Dropdowns should match site-wide styling                         | Medium   |
| UI_TC_12   | Check profile picture upload button visibility             | Look for upload button below profile pic                                  | Upload button should be visible                                  | High     |
| UI_TC_13   | Ensure tab focus works for all fields                      | Use Tab key to navigate                                                    | Cursor should shift correctly among inputs                       | Medium   |
| UI_TC_14   | Verify active/inactive state of Save button                | Observe Save button before/after editing data                             | Save button should activate only on data change                  | High     |
| UI_TC_15   | Confirm use of color contrast in text and buttons          | Check color usage on white/light background                               | Text/buttons must have sufficient contrast                       | Medium   |

---

## User Profile - Functional Test Cases

| TC ID      | Test Case Description                                      | Test Steps                                                                 | Expected Result                                                  | Priority |
|------------|------------------------------------------------------------|-----------------------------------------------------------------------------|------------------------------------------------------------------|----------|
| FUNC_TC_01 | Verify user can view profile information                   | Login > Go to Profile                                                      | All user info should be displayed correctly                      | High     |
| FUNC_TC_02 | Validate user can update name and email                    | Edit name/email > Save                                                     | Changes should persist after reload                              | High     |
| FUNC_TC_03 | Check password update functionality                        | Go to password section > Change password                                  | Password should be updated and enforced on next login            | High     |
| FUNC_TC_04 | Verify profile picture upload                              | Upload new profile picture                                                 | Picture should be saved and displayed                            | High     |
| FUNC_TC_05 | Check form validation for required fields                  | Leave required fields blank > Save                                        | Appropriate validation messages shown                            | High     |
| FUNC_TC_06 | Ensure email format validation works                       | Enter invalid email > Save                                                 | Error shown for invalid email format                             | High     |
| FUNC_TC_07 | Test cancel button functionality                           | Edit info > Click Cancel                                                   | Changes should be discarded                                      | Medium   |
| FUNC_TC_08 | Confirm gender dropdown updates correctly                  | Select gender > Save                                                       | Gender should be updated in backend                              | Medium   |
| FUNC_TC_09 | Check DOB field accepts only valid dates                   | Enter invalid date > Save                                                  | Error message shown for invalid DOB                              | High     |
| FUNC_TC_10 | Verify logout link from profile page                       | Click logout on profile page                                               | User should be logged out                                        | High     |
| FUNC_TC_11 | Validate session timeout redirects from profile            | Stay idle on profile page > Wait for timeout                              | User should be redirected to login page                          | Medium   |
| FUNC_TC_12 | Ensure security questions can be updated                   | Edit security questions > Save                                             | Answers updated and saved correctly                             | Medium   |
| FUNC_TC_13 | Check user cannot update email with one already in use     | Try to enter existing email                                                | Error shown: Email already exists                                | High     |
| FUNC_TC_14 | Verify backend is updated after saving profile             | Update phone number > Save                                                 | DB should reflect updated phone number                           | High     |
| FUNC_TC_15 | Test profile data persists after relogin                   | Logout > Login again                                                       | Profile info should remain as updated                            | High     |

---
Prepared By - **Vinayak D.**  

