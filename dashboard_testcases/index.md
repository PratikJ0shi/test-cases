# Dashboard Test Cases

This document outlines the test cases for validating the **Dashboard** functionality, with a specific focus on **Sanity** and **Role-Based Testing**. The goal is to ensure the dashboard displays the expected information based on user roles and performs its basic functions correctly.

### Objective:
To verify the functionality, usability, and accessibility of the dashboard for different user roles, ensuring it works correctly under normal and edge-case scenarios.

---

## Test Cases

### Sanity Test Cases

| TC ID          | Test Scenario                          | Test Steps                                                             | Expected Result                                                   | Priority |
|----------------|-----------------------------------------|------------------------------------------------------------------------|-------------------------------------------------------------------|----------|
| SAN_DB_01      | Verify dashboard loads successfully     | 1. Login as a valid user. <br> 2. Navigate to the dashboard.           | Dashboard should load without errors and display user data.        | High     |
| SAN_DB_02      | Verify dashboard responsiveness         | 1. Open the dashboard on multiple devices (mobile, tablet, desktop).   | Dashboard should display correctly across different screen sizes.  | High     |
| SAN_DB_03      | Verify dashboard refresh functionality  | 1. Open the dashboard. <br> 2. Refresh the page.                       | Dashboard should reload the data correctly without errors.         | High     |
| SAN_DB_04      | Verify logout functionality from dashboard | 1. Login to the dashboard. <br> 2. Click the logout button.            | User should be logged out and redirected to the login page.        | High     |
| SAN_DB_05      | Verify session expiration on inactivity | 1. Login to the dashboard. <br> 2. Wait for session to expire.         | User should be logged out automatically after session expires.     | Medium   |
| SAN_DB_06      | Verify error handling on invalid login | 1. Enter invalid credentials. <br> 2. Attempt to login.                | User should receive an error message for invalid credentials.      | High     |
| SAN_DB_07      | Verify page load time for dashboard     | 1. Login to the dashboard. <br> 2. Measure page load time.             | Page should load within an acceptable time frame (e.g., < 3 seconds). | Medium   |
| SAN_DB_08      | Verify empty state for dashboard        | 1. Login to the dashboard with no data available.                       | Dashboard should display an appropriate empty state message.       | Low      |
| SAN_DB_09      | Verify dashboard header and footer      | 1. Open the dashboard. <br> 2. Check for presence of header/footer.    | Both header and footer should be visible with correct links.       | Medium   |
| SAN_DB_10      | Verify dashboard data update            | 1. Login to the dashboard. <br> 2. Update the data manually. <br> 3. Refresh the page. | Updated data should be reflected correctly on the dashboard.       | High     |

---

### Role-Based Test Cases

| TC ID          | Test Scenario                          | Test Steps                                                             | Expected Result                                                   | Priority |
|----------------|-----------------------------------------|------------------------------------------------------------------------|-------------------------------------------------------------------|----------|
| RB_DB_01       | Verify dashboard access for admin       | 1. Login as an admin user. <br> 2. Navigate to the dashboard.          | Admin user should have full access to all dashboard features.     | High     |
| RB_DB_02       | Verify dashboard access for regular user | 1. Login as a regular user. <br> 2. Navigate to the dashboard.         | Regular user should have limited access based on permissions.     | High     |
| RB_DB_03       | Verify data visibility for admin        | 1. Login as an admin. <br> 2. Check if all data and metrics are visible on the dashboard. | Admin should be able to view all data and metrics.                | High     |
| RB_DB_04       | Verify data visibility for regular user | 1. Login as a regular user. <br> 2. Check if data is limited based on role. | Regular user should see only data they are permitted to access.   | High     |
| RB_DB_05       | Verify dashboard functionality for guest user | 1. Access the dashboard as a guest (if applicable). <br> 2. Navigate through dashboard features. | Guest user should have limited or no access to certain features.  | Medium   |
| RB_DB_06       | Verify admin-specific actions on dashboard | 1. Login as an admin user. <br> 2. Perform an action that only admins can do (e.g., editing, deleting records). | Admin should be able to perform admin-only actions.               | High     |
| RB_DB_07       | Verify restricted access for unauthorized user | 1. Attempt to access the dashboard as a user without proper permissions. | Unauthorized user should be denied access or shown an error.      | High     |
| RB_DB_08       | Verify visibility of sensitive data for admin | 1. Login as an admin. <br> 2. Check for sensitive or restricted data.  | Admin should be able to see all sensitive and restricted data.    | Medium   |
| RB_DB_09       | Verify access control on sensitive sections | 1. Login as a regular user. <br> 2. Try to access sensitive sections of the dashboard (e.g., admin settings). | Regular user should be denied access to restricted sections.      | High     |
| RB_DB_10       | Verify role-based UI elements visibility | 1. Login as an admin and a regular user. <br> 2. Compare the dashboard UI elements visible to both roles. | UI elements should differ based on user role, with admin having more controls. | Medium   |

---

### Conclusion

These test cases focus on ensuring that the dashboard is functioning correctly across different user roles. They cover both the basic sanity checks and more complex role-based permissions, ensuring that the right data and actions are visible/accessible to the appropriate users.

---

 Prepared By
**Pratik Joshi**  
