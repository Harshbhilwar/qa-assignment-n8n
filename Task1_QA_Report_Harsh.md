# QA Assessment – Bug Report & Root Cause Analysis

## Candidate
Harsh Bhilwar

## Application Under Test
RealWorld Demo Application

URL: https://demo.realworld.io

Test Date: June 2, 2026

---

# Bug Report 1

## Bug ID
BUG-001

## Title
Application homepage is inaccessible and returns HTTP 404 error

## Severity
Critical

## Priority
High

## Environment
Windows 10
Google Chrome

## Steps to Reproduce
1. Open browser
2. Navigate to https://demo.realworld.io
3. Wait for page to load

## Expected Result
Application homepage should load successfully.

## Actual Result
Application returns "404 Not Found" and users cannot access any functionality.

## Business Impact
Users are completely blocked from accessing the platform. This directly impacts user acquisition, engagement, and retention.

## Suspected Cause
Deployment, hosting configuration, DNS mapping, or cloud storage bucket misconfiguration.

---

# Bug Report 2

## Bug ID
BUG-002

## Title
Internal infrastructure information exposed on error page

## Severity
Medium

## Priority
Medium

## Steps to Reproduce
1. Open application URL
2. Observe displayed error message

## Expected Result
Users should see a generic error message.

## Actual Result
The page displays:
- Bucket Name
- Request ID
- Host ID

## Business Impact
Infrastructure information exposure may increase security risks and reveal implementation details.

## Suspected Cause
Raw cloud-storage error response exposed directly to end users.

---

# Bug Report 3

## Bug ID
BUG-003

## Title
Error page does not provide recovery options

## Severity
Medium

## Priority
Medium

## Steps to Reproduce
1. Open application URL
2. Observe error page

## Expected Result
User should see:
- Retry button
- Return Home button
- Support Contact option

## Actual Result
No recovery mechanism is available.

## Business Impact
Users have no guidance on how to proceed, increasing abandonment rate.

## Suspected Cause
Custom error handling page not implemented.

---

# Bug Report 4

## Bug ID
BUG-004

## Title
No customer support information available during outage

## Severity
Low

## Priority
Medium

## Steps to Reproduce
1. Access application
2. Observe error screen

## Expected Result
Support email or help center link should be visible.

## Actual Result
No support channel is provided.

## Business Impact
Users cannot report issues or seek assistance during outages.

## Suspected Cause
Support information omitted from failure page design.

---

# Bug Report 5

## Bug ID
BUG-005

## Title
Poor user experience during application downtime

## Severity
Low

## Priority
Low

## Steps to Reproduce
1. Open application URL
2. Observe displayed page

## Expected Result
Branded maintenance/error page with meaningful guidance.

## Actual Result
Generic technical error page shown.

## Business Impact
Reduces trust and negatively impacts user perception of product quality.

## Suspected Cause
No customized maintenance or outage page configured.

---

# Root Cause Analysis

## Selected Issue
BUG-001 – Application homepage returns HTTP 404

### Problem Statement

Users cannot access the application because the homepage fails to load and returns a 404 response.

### Evidence

The error page explicitly reports:

- Code: NoSuchBucket
- Message: The specified bucket does not exist

### Potential Root Causes

1. Cloud storage bucket deleted accidentally
2. Incorrect deployment configuration
3. Invalid DNS routing
4. Infrastructure migration issue
5. CI/CD deployment failure

### Impact Analysis

- Complete service outage
- 100% user access failure
- Potential revenue loss
- Negative user experience
- Reduced trust in platform reliability

### Recommended Fix

1. Verify cloud storage bucket existence.
2. Validate deployment pipeline.
3. Review DNS configuration.
4. Configure monitoring and alerting.
5. Implement custom outage page.

### Prevention Strategy

- Automated deployment validation
- Infrastructure monitoring
- Production health checks
- Rollback strategy
- Error-page customization

## Conclusion

The application outage appears to be caused by an infrastructure configuration issue rather than an application-level defect. Due to complete loss of access, the issue should be treated as a Critical Priority production incident.