# Search Functionality Test Cases

This document outlines the test cases for validating the **Search Functionality** in web or mobile applications. The cases are focused on ensuring the search feature works as expected across different scenarios, from basic searches to more complex and exploratory testing.

### Objective:
To verify the effectiveness, accuracy, and responsiveness of the search functionality under various conditions, ensuring the system delivers correct search results and handles edge cases efficiently.

---

## Test Cases

### End-to-End Test Cases

| TC ID          | Test Scenario                          | Test Steps                                                             | Expected Result                                                   | Priority |
|----------------|-----------------------------------------|------------------------------------------------------------------------|-------------------------------------------------------------------|----------|
| E2E_SF_01      | Search with valid keyword               | 1. Enter valid search term in the search bar. <br> 2. Press enter or click search. | Relevant search results should be displayed.                      | High     |
| E2E_SF_02      | Search with invalid keyword             | 1. Enter an invalid or non-existent keyword. <br> 2. Press enter or click search. | Display “No results found” or relevant message.                  | High     |
| E2E_SF_03      | Search with special characters          | 1. Enter special characters in the search bar (e.g., @, #, %). <br> 2. Press enter or click search. | Results should be filtered or show relevant data if available.    | Medium   |
| E2E_SF_04      | Search with empty query                 | 1. Leave the search bar empty. <br> 2. Press enter or click search.    | Display a prompt: “Please enter a search term.”                   | High     |
| E2E_SF_05      | Search with multiple keywords           | 1. Enter multiple keywords separated by spaces (e.g., "Laptop Dell"). <br> 2. Press enter or click search. | Results should match the combination of keywords.                 | High     |
| E2E_SF_06      | Search case sensitivity check           | 1. Enter a search term with different cases (e.g., "laptop" and "Laptop"). <br> 2. Press enter or click search. | Results should not be case-sensitive and should return the same results. | Medium   |
| E2E_SF_07      | Search with filters applied             | 1. Apply filters (e.g., category, price range). <br> 2. Enter a search term and press enter. | Results should reflect the filter criteria along with the search. | High     |
| E2E_SF_08      | Check pagination in search results      | 1. Perform a search query that results in multiple pages of results. <br> 2. Navigate between pages. | Pagination should work correctly, and new results should load.    | Medium   |
| E2E_SF_09      | Search for exact match                  | 1. Search for an exact match keyword (e.g., product name). <br> 2. Press enter or click search. | Exact match should appear at the top of the results.              | High     |
| E2E_SF_10      | Verify search result relevance          | 1. Perform a search query. <br> 2. Review results for relevance.      | Results should be relevant to the query and sorted correctly.     | High     |

---

### Exploratory Test Cases

| TC ID          | Test Scenario                          | Test Steps                                                             | Expected Result                                                   | Priority |
|----------------|-----------------------------------------|------------------------------------------------------------------------|-------------------------------------------------------------------|----------|
| EX_SF_01       | Test search with mixed characters       | 1. Enter a search term with a mix of special characters and numbers. (e.g., "Lap#123$") | System should process the term correctly or sanitize if necessary. | Medium   |
| EX_SF_02       | Test search performance with large data | 1. Search for a common term in a large dataset. <br> 2. Measure the response time. | Search should complete within an acceptable time (e.g., < 2 seconds). | High     |
| EX_SF_03       | Test search with misspelled query       | 1. Enter a search term with a common spelling mistake (e.g., "laptop" as "laptp"). | System should either suggest the correct term or show relevant results. | Medium   |
| EX_SF_04       | Test search behavior with multi-language input | 1. Enter a search term in different languages (e.g., "ordinateur" for French). | System should handle multilingual queries appropriately.          | Medium   |
| EX_SF_05       | Test search with SQL Injection attempt   | 1. Enter an SQL injection attempt (e.g., “' OR 1=1 --”) in the search bar. | Application should sanitize input and not allow SQL injection.    | High     |
| EX_SF_06       | Test search after clearing the cache     | 1. Clear browser cache. <br> 2. Perform a search.                      | Results should still be consistent after clearing the cache.      | Medium   |
| EX_SF_07       | Test search with a long query string     | 1. Enter a very long search query (e.g., 100+ characters). | The system should handle long input gracefully without errors.    | Low      |
| EX_SF_08       | Test search with auto-suggestions enabled | 1. Start typing a search term. <br> 2. Observe auto-suggestions. | Auto-suggestions should appear and be relevant.                   | Medium   |
| EX_SF_09       | Test search with no internet connection  | 1. Disable internet connection. <br> 2. Perform a search.             | The application should handle the no-connection scenario gracefully. | High     |
| EX_SF_10       | Test search and result click behavior    | 1. Perform a search. <br> 2. Click on one of the results. | The system should navigate to the corresponding page or details.  | High     |

---

### Conclusion

These test cases cover a wide range of scenarios related to the search functionality, from end-to-end validation to exploratory testing for edge cases and performance checks. By executing these tests, you can ensure that the search feature is not only functional but also resilient to potential user errors, large datasets, and security risks.

---

 Prepared By
**Pratik Joshi**  

