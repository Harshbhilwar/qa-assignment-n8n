# QA Assignment Report

## Objective

Create an n8n workflow using API integration, conditional logic, notifications, and error handling.

## Test Scenario

### Test Case 1

Input:
CoinGecko API Response

Expected:
Top cryptocurrency data retrieved.

Result:
PASS

---

### Test Case 2

Input:
Bitcoin market_cap_rank = 1

Expected:
IF node evaluates TRUE.

Result:
PASS

---

### Test Case 3

Input:
TRUE branch

Expected:
Discord notification sent.

Result:
PASS

---

### Test Case 4

Input:
API Failure

Expected:
Workflow continues execution.

Result:
PASS

## Conclusion

Workflow executed successfully and all test cases passed.