# logout_test_cases

| TC No. | Test Case Description                          | Steps                                                                 | Expected Result                                                        | Priority |
|--------|------------------------------------------------|------------------------------------------------------------------------|------------------------------------------------------------------------|----------|
| TC01   | Successful Logout                              | Login → Click Logout                                                  | User is logged out and redirected to login page.                       | High     |
| TC02   | Session Termination                            | Logout → Try accessing a secure page via browser history              | Redirects to login page (session expired).                             | High     |
| TC03   | Logout from Header/Menu                        | Click Logout from top menu                                            | User is logged out correctly.                                          | High     |
| TC04   | Logout Button Clickable                        | Observe Logout button                                                 | Button is enabled and clickable.                                       | Medium   |
| TC05   | Logout Confirmation Prompt                     | Click Logout                                                          | Confirmation popup appears (Yes/No).                                   | Medium   |
| TC06   | Cancel Logout                                  | Click Logout → Cancel on confirmation                                 | User remains logged in.                                                | Low      |
| TC07   | Auto Logout after Inactivity                   | Stay idle for session timeout duration                                | User is automatically logged out.                                      | High     |
| TC08   | Logout from One Device Doesn’t Affect Another | Login from 2 devices → Logout from one                                | Second session stays active (if supported).                            | Medium   |
| TC09   | Logout from All Devices                        | Click “Logout from all devices”                                       | All active sessions are terminated.                                    | Medium   |
| TC10   | Direct Access After Logout                     | Logout → Enter dashboard URL manually                                 | Redirects to login page.                                               | High     |
| TC11   | Logout Button Placement                        | Check Logout button location                                          | Clearly visible in UI header/menu.                                     | Medium   |
| TC12   | Logout Icon Display                            | Observe logout icon (if used)                                         | Proper icon aligned with logout label.                                 | Low      |
| TC13   | Responsive Behavior                            | Open on mobile/tablet view                                            | Logout button accessible and visible.                                  | Medium   |
| TC14   | Logout Without Login                           | Access logout URL directly                                            | Redirects to login page or error message shown.                        | High     |
| TC15   | Broken Session Handling                        | Modify session token manually → Click logout                          | Logout fails gracefully with proper message.                           | Medium   |
| TC16   | Browser Back After Logout                      | Logout → Click browser back                                           | No access to previous page, stays on login screen.                     | High     |
| TC17   | Logout and Cache                               | Logout → Reopen tab                                                   | No user data visible; session is cleared.                              | High     |
| TC18   | Browser Refresh After Logout                   | Logout → Refresh page                                                 | Remains on login page.                                                 | High     |
| TC19   | Logout One User and Login Another              | User A logs out → User B logs in                                      | No session conflict or data leakage.                                   | Medium   |
| TC20   | Concurrent Logout While Performing Action      | Logout from another tab → Try submitting form                         | Action blocked, redirected to login page.                              | High     |

---
## positive

| POS_ID  | Test Case Description                          | Steps                                                            | Expected Result                                                   | Priority |
|---------|------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|----------|
| POS001  | Successful Logout                              | Login → Click Logout                                             | User is logged out and redirected to login page.                | High     |
| POS002  | Logout via Header Menu                         | Click Logout from header                                         | User is logged out and redirected to login page.                | High     |
| POS003  | Logout via Profile Dropdown                    | Click Logout from user profile dropdown                          | Logout completes and user lands on login page.                  | Medium   |
| POS004  | Auto Logout on Inactivity                      | Wait idle until session timeout                                  | User is auto-logged out and redirected to login screen.         | High     |
| POS005  | Logout from Multiple Tabs                      | Open 2 tabs → Logout from one → Other tab is logged out          | All tabs reflect logged-out state.                              | High     |
| POS006  | Logout from Mobile View                        | Login on mobile → Click Logout                                   | Logged out successfully with mobile-friendly layout.            | Medium   |
| POS007  | Logout from Tablet View                        | Login on tablet → Click Logout                                   | Logout behaves correctly on tablet view.                        | Medium   |
| POS008  | Logout Button Visibility                       | Observe UI after login                                           | Logout button is visible and accessible.                        | Low      |
| POS009  | Logout Button Functionality                    | Click Logout button                                              | Button works, ends session and redirects properly.              | High     |
| POS010  | Logout with Active Internet                    | Ensure network is stable → Logout                                | Logout executes without errors.                                 | High     |
| POS011  | Logout Button Accessible via Keyboard          | Navigate with Tab key to Logout → Press Enter                    | Logout triggered via keyboard works.                            | Medium   |
| POS012  | Logout on Slow Connection                      | Throttle network → Logout                                        | Logout still works with slight delay.                           | Medium   |
| POS013  | Logout UI Label is Correct                     | Verify label of logout button                                    | Label says "Logout" or equivalent clearly.                      | Low      |
| POS014  | Logout After Performing Actions                | Fill a form → Submit → Logout                                    | Logout clears session and returns to login.                     | High     |
| POS015  | Logout then Re-login                           | Logout → Login again                                             | New session starts fresh without old data.                      | High     |
| POS016  | Logout from Footer                             | Click Logout in footer (if provided)                             | Logout completes successfully.                                  | Medium   |
| POS017  | Logout Confirmation Modal                      | Click Logout → Confirmation modal appears                        | Modal asks for user confirmation.                               | Medium   |
| POS018  | Cancel Logout from Modal                       | Click Logout → Cancel in modal                                   | User remains logged in.                                         | Low      |
| POS019  | Logout via Shortcut (e.g., Ctrl+Shift+L)       | Use app shortcut to logout                                       | Session ends and redirects to login.                            | Medium   |
| POS020  | Logout After Password Change                   | Change password → Logout → Login again                           | Old session ends, new login works.                              | High     |

---

## negative
| NEG_ID  | Test Case Description                          | Steps                                                            | Expected Result                                                   | Priority |
|---------|------------------------------------------------|------------------------------------------------------------------|------------------------------------------------------------------|----------|
| NEG001  | Logout Without Login                           | Directly access logout URL without login                         | Redirects to login or error shown.                              | High     |
| NEG002  | Logout with Expired Session                    | Let session expire → Click Logout                               | Error handled gracefully.                                       | High     |
| NEG003  | Tampered Session Cookie                        | Modify session cookie manually → Click Logout                    | Logout fails gracefully or redirects to login.                  | Medium   |
| NEG004  | Logout via Corrupted Token                     | Use a bad session token                                          | Logs out and clears corrupted data.                             | Medium   |
| NEG005  | Logout from Non-existent User Session          | Simulate deleted user session → Click Logout                    | Error shown or logout succeeds silently.                        | Medium   |
| NEG006  | Double Click Logout                            | Rapid double-click logout button                                 | Handled without errors, logs out once.                          | Low      |
| NEG007  | Logout While Server Is Down                    | Simulate backend unavailability → Try logout                     | Proper error shown or handled gracefully.                       | High     |
| NEG008  | Logout with JavaScript Disabled                | Disable JS in browser → Try clicking logout                      | Button fails gracefully or alternative method used.             | Medium   |
| NEG009  | Logout Button Not Visible                      | Hide logout button via CSS/browser tools                         | Accessibility failure detected.                                 | Medium   |
| NEG010  | Logout URL Tampering                           | Modify logout URL                                                | Application handles invalid URL securely.                       | Medium   |
| NEG011  | Logout When Already Logged Out                 | Logout → Try logout again                                        | Stays on login page or shows "Already logged out."              | Low      |
| NEG012  | Logout from Unauthorized Role                  | Login as unauthorized role → Access logout                       | Access denied or redirects.                                     | Medium   |
| NEG013  | Logout with Network Interrupted                | Disable network mid-logout                                       | Graceful fallback or retry option.                              | High     |
| NEG014  | Logout During Data Submission                  | Submit form → Immediately click logout                           | Either form submits or safe logout handled.                     | Medium   |
| NEG015  | Logout with Browser Crash                      | Crash tab during logout → Reopen                                 | No session restored; re-login required.                         | Medium   |
| NEG016  | Click Disabled Logout Button                   | Set logout button to disabled state → Try clicking               | Nothing happens, UI blocked.                                    | Low      |
| NEG017  | Invalid Logout Request Method (e.g., GET)      | Send logout via GET instead of POST                              | Rejected or redirected securely.                                | Medium   |
| NEG018  | Logout from Unauthorized Page                  | Try logging out from restricted area without permission          | Redirect to login with error message.                           | Medium   |
| NEG019  | Logout Link Redirects to Wrong Page            | Misconfigured logout → Redirects to wrong path                   | Bug detected; should go to login.                               | High     |
| NEG020  | Logout Button Missing                          | Logout not present in UI                                         | Critical issue; fails UI/UX test.                               | High     |


------
## sanity
| **Test Case ID** | **Test Case Description**                                  | **Test Steps**                                                                                                                                               | **Expected Outcome**                                       | **Priority** |
|------------------|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|--------------|
| S1               | Verify if the logout button is visible on the application. | 1. Open the application. <br> 2. Navigate to the page with the logout button. <br> 3. Check if the logout button is visible. | Logout button should be visible in the header/footer.      | High         |
| S2               | Verify if the user can successfully click on the logout button. | 1. Open the application. <br> 2. Locate the logout button. <br> 3. Click the logout button. | Upon clicking the logout button, the user should be logged out. | High         |
| S3               | Check if the logout process redirects to the login page.  | 1. Click the logout button. <br> 2. Observe the page transition. | User should be redirected to the login page after logout. | High         |
| S4               | Verify that the session is destroyed after logout.       | 1. Click the logout button. <br> 2. Try to access the dashboard or another authenticated page. | After logout, the user session should no longer be active. | High         |
| S5               | Ensure that the login page is displayed after logout.     | 1. Click the logout button. <br> 2. Verify that the login page appears with fields to re-enter credentials. | Login page should display with fields to re-enter credentials. | Medium       |
| S6               | Verify that the user cannot access the dashboard after logout. | 1. Logout from the application. <br> 2. Try to access the dashboard directly via URL. | Trying to access the dashboard after logout should show a login screen. | High         |
| S7               | Ensure that no personal information is retained after logout. | 1. Logout from the application. <br> 2. Verify that no personal information is displayed on the login page. | No personal data should be available after logout.         | Medium       |
| S8               | Verify that clicking logout logs the user out across all open tabs. | 1. Open multiple tabs in the browser. <br> 2. Click the logout button in one tab. <br> 3. Check the other tabs to verify logout. | User should be logged out from all active browser tabs.    | High         |
| S9               | Ensure the logout button works across all screen sizes.   | 1. Open the application on different devices (desktop, tablet, mobile). <br> 2. Check if the logout button is functional on each device. | Logout button should work seamlessly on desktop and mobile. | High         |
| S10              | Verify that clicking logout logs the user out of integrated services. | 1. Logout from the application. <br> 2. Check if the user is logged out from integrated services (e.g., Google, Facebook). | User should be logged out from third-party services integrated into the app. | Medium       |
| S11              | Check if the system provides any confirmation for logging out. | 1. Click the logout button. <br> 2. Check if there is a confirmation dialog before logout. | System may display a confirmation message before logging out. | Low          |
| S12              | Verify logout behavior when multiple sessions are active. | 1. Log in to the application on multiple devices or browsers. <br> 2. Click the logout button on one device. | User should be logged out of all active sessions.           | High         |
| S13              | Ensure that after logout, clicking the back button shows the login page. | 1. Logout from the application. <br> 2. Click the browser’s back button. | Clicking the browser’s back button after logout should display the login page. | Low          |
| S14              | Check if the session token is invalidated after logout.   | 1. Logout from the application. <br> 2. Try to reuse the session token. | Session token should be invalidated to prevent reuse.      | Medium       |
| S15              | Verify that no errors occur when attempting to log out repeatedly. | 1. Logout from the application multiple times. | No errors should be triggered when logging out multiple times. | Low          |



-------
## retest

| **Test Case ID** | **Test Case Description**                                  | **Test Steps**                                                                                                                                               | **Expected Outcome**                                       | **Priority** |
|------------------|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|--------------|
| R1               | Retest logout functionality after bug fix.                | 1. Ensure the bug fix is implemented. <br> 2. Log in to the application. <br> 3. Click the logout button. | Logout functionality should work as expected after the bug fix. | High         |
| R2               | Verify that the session is terminated after logout fix.   | 1. Log in to the application. <br> 2. Click the logout button. <br> 3. Attempt to access the app again. | User session should be destroyed after logout.              | High         |
| R3               | Verify that user is redirected to the login page after logout. | 1. Log in to the application. <br> 2. Click the logout button. <br> 3. Check the redirection to the login page. | User should be redirected to the login page after logging out. | High         |
| R4               | Verify logout works when user is logged in with different roles. | 1. Log in with a user role. <br> 2. Click the logout button. <br> 3. Verify that the user is logged out. | Users should be logged out from their respective roles after logout. | Medium       |
| R5               | Retest logout functionality after browser compatibility fix. | 1. Open the application in different browsers. <br> 2. Click the logout button in each browser. | Logout should work in all supported browsers.               | High         |
| R6               | Verify if the session cookies are deleted after logout.   | 1. Log in to the application. <br> 2. Click the logout button. <br> 3. Check if the cookies are deleted. | Session cookies should be cleared after logout.             | Medium       |
| R7               | Retest the logout functionality when multiple tabs are open. | 1. Open multiple tabs in the same browser. <br> 2. Click the logout button in one tab. <br> 3. Verify logout across all tabs. | User should be logged out from all open tabs after clicking logout. | High         |
| R8               | Check if the logout function works for users who have been inactive for a long time. | 1. Leave the application idle for a set time. <br> 2. Check if the user is logged out due to inactivity. | Users should be logged out after long periods of inactivity. | Medium       |
| R9               | Verify that clicking logout once logs the user out of all services. | 1. Log in to the app with an integrated service (e.g., Google). <br> 2. Click the logout button. <br> 3. Check if the user is logged out of the integrated service as well. | User should be logged out of all active services, not just the app. | Medium       |
| R10              | Ensure logout does not affect other parts of the system.  | 1. Perform actions in other parts of the system. <br> 2. Click the logout button. | Other parts of the system should function normally post-logout. | Low          |
| R11              | Retest logout functionality after user role changes.      | 1. Change the user’s role in the system. <br> 2. Click the logout button. | User should be logged out properly after a role change.     | Medium       |
| R12              | Check if logout works when the application is in a background state. | 1. Minimize the application. <br> 2. Click the logout button. | User should be logged out even if the app is in the background. | Low          |
| R13              | Verify the logout functionality when the app is restarted. | 1. Log in to the app. <br> 2. Restart the app. <br> 3. Check if the user remains logged out. | User should remain logged out even after restarting the app. | High         |
| R14              | Verify that clicking logout once logs the user out from all services. | 1. Log in to the app. <br> 2. Click the logout button. <br> 3. Verify logout in other connected services. | User should be logged out of all active services, not just the app. | Medium       |
| R15              | Retest logout behavior when using single sign-on (SSO).   | 1. Log in using SSO (e.g., Google). <br> 2. Click the logout button. <br> 3. Verify the user is logged out from both the app and the SSO service. | User should be logged out from both the app and SSO service. | High         |


------
## regression

| **Test Case ID** | **Test Case Description**                                  | **Test Steps**                                                                                                                                               | **Expected Outcome**                                       | **Priority** |
|------------------|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|--------------|
| G1               | Verify logout functionality after a system update.         | 1. Perform system update. <br> 2. Log in to the application. <br> 3. Click the logout button. | Logout functionality should work after the system update. | High         |
| G2               | Verify that logout does not affect other features of the app. | 1. Log in to the app. <br> 2. Perform actions in other app features. <br> 3. Click the logout button. | Other app features should remain unaffected by logout.     | High         |
| G3               | Check if the logout button works correctly after a bug fix. | 1. Log in to the app. <br> 2. Click the logout button. | Logout functionality should work correctly after a fix.    | High         |
| G4               | Verify that no data is cached after logout.                | 1. Log in to the app. <br> 2. Click the logout button. <br> 3. Verify that no cached data is retained. | No data should be cached after logout.                    | Medium       |
| G5               | Verify if the session is invalidated after logout in different browsers. | 1. Log in to the app in different browsers. <br> 2. Click the logout button. | User session should be invalidated across all browsers.    | High         |
| G6               | Ensure the logout button still works after an app update.  | 1. Update the app to the latest version. <br> 2. Log in and click the logout button. | Logout should work seamlessly after the update.            | High         |
| G7               | Verify logout functionality in incognito or private browsing mode. | 1. Open the app in incognito/private mode. <br> 2. Log in and click the logout button. | Logout should work in incognito mode.                      | Medium       |
| G8               | Ensure that session cookies are cleared after logout.      | 1. Log in to the app. <br> 2. Click the logout button. <br> 3. Check if cookies are deleted. | Session cookies should be deleted post-logout.             | Medium       |
| G9               | Verify that the login page is displayed after logout on multiple devices. | 1. Log in to the app on multiple devices. <br> 2. Click the logout button. | Login page should be displayed on all devices after logout. | High         |
| G10              | Check if logging out clears any session data stored in the local storage. | 1. Log in to the app. <br> 2. Click the logout button. <br> 3. Check if the local storage is cleared. | Local storage data should be cleared after logout.         | Medium       |
| G11              | Verify logout functionality works when user is switched between networks (Wi-Fi/Data). | 1. Log in on the app. <br> 2. Switch networks from Wi-Fi to Data or vice versa. <br> 3. Click the logout button. | Logout should work without issue when switching networks.  | Medium       |
| G12              | Verify that after logout, all user data is properly removed from the server. | 1. Log in to the app. <br> 2. Click logout. <br> 3. Verify that the user data is removed from the server. | No personal data should be available post-logout.          | High         |
| G13              | Check if logout functionality works when user has multiple active sessions. | 1. Log in from multiple devices. <br> 2. Click the logout button. | User should be logged out from all devices.                | High         |
| G14              | Verify if logout process works on both authenticated and unauthenticated pages. | 1. Log in to the app. <br> 2. Visit authenticated and unauthenticated pages. <br> 3. Click the logout button. | Logout should work seamlessly regardless of page type.     | Medium       |
| G15              | Ensure no errors are triggered during logout after extensive usage. | 1. Use the app for a prolonged period. <br> 2. Log out. | No errors should occur during the logout process after prolonged usage. | Low          |


-------


## smoke

| **Test Case ID** | **Test Case Description**                                  | **Test Steps**                                                                                                                                               | **Expected Outcome**                                       | **Priority** |
|------------------|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|--------------|
| S1               | Verify if the logout button is accessible.                 | 1. Open the application. <br> 2. Check if the logout button is visible and clickable. | Logout button should be accessible and clickable.          | High         |
| S2               | Ensure the logout button triggers the logout process.      | 1. Log in to the app. <br> 2. Click the logout button. | User should be logged out immediately after clicking the button. | High         |
| S3               | Verify user is redirected to the login page after logout.  | 1. Log in to the app. <br> 2. Click the logout button. | User should be redirected to the login page after logout.  | High         |
| S4               | Ensure no user data remains after logout.                  | 1. Log in to the app. <br> 2. Click the logout button. <br> 3. Verify no user data is visible on the login page. | No data should remain post-logout.                         | Medium       |
| S5               | Verify that clicking the logout button terminates the session. | 1. Log in to the app. <br> 2. Click the logout button. | User session should be terminated and inaccessible.        | High         |
| S6               | Verify the logout button works across different browsers.  | 1. Open the app on different browsers. <br> 2. Click the logout button in each browser. | Logout functionality should work across browsers.          | High         |
| S7               | Ensure logout works when the app is restarted.             | 1. Log in to the app. <br> 2. Restart the app. <br> 3. Check if the user is logged out. | User should remain logged out after the app restart.       | High         |
| S8               | Verify that the user cannot access secured pages post-logout. | 1. Log out of the app. <br> 2. Try accessing a secured page. | Access should be denied and redirect to the login page.    | High         |
| S9               | Ensure logout works when the user is inactive for a long time. | 1. Leave the app inactive for an extended time. <br> 2. Check if the user is logged out. | User should be logged out due to inactivity.               | Medium       |
| S10              | Verify that session cookies are cleared after logout.      | 1. Log in to the app. <br> 2. Click the logout button. <br> 3. Check the session cookies. | Session cookies should be deleted after logout.            | High         |
| S11              | Ensure the app behaves normally after logout.              | 1. Log out from the app. <br> 2. Perform other app actions. | App should function normally post-logout.                 | Medium       |
| S12              | Verify logout functionality on mobile and desktop devices. | 1. Log in to the app. <br> 2. Click the logout button. <br> 3. Verify logout on both desktop and mobile. | Logout should work on both devices.                        | High         |
| S13              | Verify the logout button works after app is minimized.     | 1. Minimize the app. <br> 2. Open the app again. <br> 3. Click the logout button. | Logout should work after the app is minimized.             | Medium       |
| S14              | Check if logout works with multiple tabs open.             | 1. Open multiple tabs in the browser. <br> 2. Click the logout button in one tab. | User should be logged out from all active tabs.            | High         |
| S15              | Ensure the app does not crash upon clicking logout.        | 1. Click the logout button. | No crashes or errors should occur upon clicking logout.    | High         |


----

## e2e

| **Test Case ID** | **Test Case Description**                                  | **Test Steps**                                                                                                                                               | **Expected Outcome**                                       | **Priority** |
|------------------|------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------|--------------|
| E1               | Verify the entire logout process with valid credentials.    | 1. Open the application. <br> 2. Log in with valid credentials. <br> 3. Click the logout button. <br> 4. Verify the user is logged out and redirected to the login page. | User should be logged out and redirected to the login page. | High         |
| E2               | Ensure logout process works after navigating to different pages. | 1. Log in to the app. <br> 2. Navigate to different pages (dashboard, profile, etc.). <br> 3. Click the logout button. | User should be logged out and redirected to the login page. | High         |
| E3               | Verify logout when multiple services are integrated.       | 1. Log in with an integrated service (e.g., Google). <br> 2. Click the logout button. <br> 3. Verify that the user is logged out from the app and integrated service. | User should be logged out from the app and integrated services. | Medium       |
| E4               | Verify logout functionality across different devices.      | 1. Log in to the app on multiple devices. <br> 2. Click the logout button. | User should be logged out from all devices.                | High         |
| E5               | Verify that no user data is retained after logout.         | 1. Log in to the app. <br> 2. Click the logout button. <br> 3. Verify that no user data is retained or displayed. | No personal data should be displayed after logout.         | Medium       |
| E6               | Ensure no errors occur during the logout process.          | 1. Log in to the app. <br> 2. Click the logout button. <br> 3. Observe if any errors occur. | No errors should occur during the logout process.          | High         |
| E7               | Verify logout functionality after the app is restarted.    | 1. Log in to the app. <br> 2. Restart the app. <br> 3. Verify that the user remains logged out. | User should remain logged out after restarting the app.    | High         |
| E8               | Check if logout works across both mobile and desktop platforms. | 1. Log in to the app on both desktop and mobile. <br> 2. Click the logout button on each platform. | Logout should work on both desktop and mobile.             | High         |
| E9               | Ensure user is redirected to login page after logout on all platforms. | 1. Log in to the app. <br> 2. Click logout. <br> 3. Verify redirection to the login page. | User should be redirected to the login page on all platforms. | High         |
| E10              | Verify session termination after logout across all tabs.   | 1. Open multiple tabs with the app. <br> 2. Click logout in one tab. | User should be logged out from all active tabs.            | High         |

----
**Prepared by:** [Pratik Joshi]   
**Module:** | Form Testing | logout-testcases |
