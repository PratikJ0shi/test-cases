# Checkout & Payment Test Cases

This document outlines the test cases for validating the **Checkout & Payment** functionality. The focus is on ensuring that the checkout process integrates properly with payment systems, works as expected in regression scenarios, and ensures the entire process runs end-to-end successfully.

### Objective:
To verify the functionality of the checkout process, including payment integration and end-to-end user flow from adding items to the cart to confirming the payment.

---

## Test Cases

### Integration Test Cases

| TC ID          | Test Scenario                                 | Test Steps                                                             | Expected Result                                                   | Priority |
|----------------|------------------------------------------------|------------------------------------------------------------------------|-------------------------------------------------------------------|----------|
| INT_CK_01      | Verify payment gateway integration            | 1. Add items to the cart. <br> 2. Proceed to checkout. <br> 3. Select payment method (e.g., Credit Card). | Payment gateway should be integrated and process payment correctly. | High     |
| INT_CK_02      | Verify order details are passed to payment system | 1. Add items to the cart. <br> 2. Proceed to checkout. <br> 3. Review order details before payment. | Order details should be sent correctly to the payment system.     | High     |
| INT_CK_03      | Verify payment confirmation from payment gateway | 1. Select payment method and complete payment. <br> 2. Check payment gateway for confirmation. | Payment gateway should confirm the payment successfully.          | High     |
| INT_CK_04      | Verify successful transaction after payment    | 1. Complete the payment process. <br> 2. Check order status in the user profile. | Order should be marked as "paid" and show correct status.         | High     |
| INT_CK_05      | Verify error handling for failed payment      | 1. Choose a payment method that will fail (e.g., invalid card). <br> 2. Complete the payment process. | User should receive an error message explaining payment failure.   | High     |
| INT_CK_06      | Verify payment system works with multiple currencies | 1. Add items to the cart. <br> 2. Change the currency (e.g., USD to EUR). <br> 3. Proceed to checkout. | Payment should process correctly in the selected currency.        | Medium   |
| INT_CK_07      | Verify discount code integration with checkout | 1. Add items to cart. <br> 2. Apply discount code. <br> 3. Proceed to checkout and complete payment. | Discount should be applied correctly during payment.              | Medium   |
| INT_CK_08      | Verify fraud detection during payment         | 1. Add items to the cart. <br> 2. Enter suspicious payment details. <br> 3. Complete payment. | Payment gateway should flag suspicious transactions.              | High     |
| INT_CK_09      | Verify payment method update functionality    | 1. Add items to the cart. <br> 2. Update payment method (e.g., change from Credit Card to PayPal). <br> 3. Complete checkout. | Payment method should update and complete checkout successfully.  | Medium   |
| INT_CK_10      | Verify payment retry mechanism                | 1. Add items to the cart. <br> 2. Attempt to complete payment with an error. <br> 3. Retry payment. | Payment should be retried successfully after failure.             | High     |

---

### Regression Test Cases

| TC ID          | Test Scenario                                 | Test Steps                                                             | Expected Result                                                   | Priority |
|----------------|------------------------------------------------|------------------------------------------------------------------------|-------------------------------------------------------------------|----------|
| REG_CK_01      | Verify payment gateway works after updates    | 1. Update payment gateway settings (if applicable). <br> 2. Complete a payment. | Payment gateway should process payments successfully after update. | High     |
| REG_CK_02      | Verify discount code functionality            | 1. Add items to cart. <br> 2. Apply a valid discount code. <br> 3. Complete checkout. | Discount should be applied correctly to the total.                | Medium   |
| REG_CK_03      | Verify item availability during checkout      | 1. Add out-of-stock item to cart. <br> 2. Attempt to checkout.        | User should not be able to proceed with out-of-stock items.        | High     |
| REG_CK_04      | Verify payment method selection works         | 1. Add items to the cart. <br> 2. Choose different payment methods (e.g., PayPal, Credit Card). | User should be able to select and complete payment using all supported methods. | High     |
| REG_CK_05      | Verify shipping details update after payment   | 1. Add items to the cart. <br> 2. Proceed to checkout and complete payment. <br> 3. Check shipping details in order confirmation. | Shipping details should update based on payment completion.       | Medium   |
| REG_CK_06      | Verify applied tax calculation during checkout | 1. Add items to cart. <br> 2. Proceed to checkout. <br> 3. Check applied taxes. | Correct taxes should be applied based on location and items.      | Medium   |
| REG_CK_07      | Verify user can change payment method before finalizing checkout | 1. Add items to cart. <br> 2. Choose a payment method. <br> 3. Change payment method before finalizing. | User should be able to change the payment method without issues.   | High     |
| REG_CK_08      | Verify order summary after coupon application | 1. Add items to cart. <br> 2. Apply a coupon code. <br> 3. Complete checkout. | Coupon discount should be reflected in the order summary.         | Medium   |
| REG_CK_09      | Verify return policy displayed during checkout | 1. Add items to cart. <br> 2. Proceed to checkout. <br> 3. Check return policy link. | Return policy should be visible during the checkout process.      | Low      |
| REG_CK_10      | Verify successful payment record update after retry | 1. Attempt payment, fail, then retry with a successful transaction. | Payment status should reflect a successful transaction after retry. | High     |

---

### End-to-End (E2E) Test Cases

| TC ID          | Test Scenario                                 | Test Steps                                                             | Expected Result                                                   | Priority |
|----------------|------------------------------------------------|------------------------------------------------------------------------|-------------------------------------------------------------------|----------|
| E2E_CK_01      | Complete checkout process with payment        | 1. Add items to cart. <br> 2. Proceed to checkout. <br> 3. Complete payment. | Order should be successfully placed and payment confirmed.        | High     |
| E2E_CK_02      | Verify order summary after checkout           | 1. Add items to cart. <br> 2. Proceed to checkout. <br> 3. Complete payment. <br> 4. View order summary. | Order summary should match the items, prices, and shipping info.  | High     |
| E2E_CK_03      | Verify payment method transition              | 1. Add items to cart. <br> 2. Choose multiple payment methods. <br> 3. Complete checkout with each method. | Payment methods should transition smoothly, and payment should be processed. | High     |
| E2E_CK_04      | Verify email confirmation after order placed  | 1. Complete the checkout process. <br> 2. Check email for order confirmation. | User should receive an email with the order details and payment confirmation. | High     |
| E2E_CK_05      | Verify full cycle of cart to checkout with coupon | 1. Add items to the cart. <br> 2. Apply a coupon. <br> 3. Proceed to checkout and complete payment. | Coupon should be applied correctly, and order should be successfully placed. | Medium   |
| E2E_CK_06      | Verify successful cart to checkout process on mobile | 1. Add items to the cart on mobile. <br> 2. Proceed to checkout. <br> 3. Complete payment on mobile. | Checkout and payment process should work seamlessly on mobile.    | High     |
| E2E_CK_07      | Verify refund process after checkout          | 1. Complete payment. <br> 2. Initiate refund request. <br> 3. Verify refund confirmation. | Refund should be processed successfully after order cancellation. | Medium   |
| E2E_CK_08      | Verify that order status is updated post-payment | 1. Add items to the cart. <br> 2. Complete checkout. <br> 3. Check the order status. | Order status should be updated to "Paid" after payment completion. | High     |
| E2E_CK_09      | Verify guest checkout and order confirmation  | 1. Add items to cart as a guest. <br> 2. Proceed to checkout. <br> 3. Complete payment. | Order should be successfully placed and confirmation received for guest checkout. | High     |
| E2E_CK_10      | Verify no errors during repeated checkout with same items | 1. Add items to cart. <br> 2. Complete payment. <br> 3. Repeat checkout process for same items. | The checkout process should not throw errors with repeated items. | Medium   |

---

### Conclusion

These test cases focus on verifying the checkout and payment functionality across different testing stages, including integration with payment gateways, regression testing for stable operations after updates, and end-to-end testing of the full transaction cycle from cart to payment confirmation.

---

 Prepared By
**Pratik Joshi**  
