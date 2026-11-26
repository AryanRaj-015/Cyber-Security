# Activity: Access Control Review

- **Course:** Google Cybersecurity Certificate - Course 5 (Assets, Threats, and Vulnerabilities)
- **Platform:** Google Skills
- **Category:** Access Control and Authorization
- **Materials reviewed:** Access-control worksheet, employee directory, and event log

## Objective

Assess whether employee access is appropriate for assigned roles, review a sensitive payroll event in context, and recommend controls that reduce the risk of unauthorized access.

## Scenario

The worksheet describes a shared cloud drive where employees can access company resources and all users have administrative privileges. The supporting employee directory lists user roles and authorization levels, while an event log records a payroll-related change.

## Method

1. Reviewed the access-control worksheet to identify how shared-drive permissions were assigned.
2. Compared roles and authorization levels in the employee directory to assess whether access followed least privilege.
3. Reviewed the event type, account, time, device, and IP address in the event log, then compared those details with the directory entry for the corresponding role.
4. Used the evidence to identify access-control weaknesses and propose corrective measures.

## Findings

| Finding | Evidence | Risk |
|---|---|---|
| Employees have broad administrative access | The worksheet says all employees can access organizational resources through a shared drive and hold administrative privileges. The directory also lists Admin authorization across its entries. | Excessive permissions can expose sensitive information and allow users to make changes outside their job responsibilities. |
| A payroll event is associated with an administrator account for a legal role | The event log records a payroll event under `Legal\Administrator`; the supporting records provide matching account context. | Sensitive financial activity should be restricted to authorized roles and reviewed. The log entry alone does not establish whether the activity was authorized or malicious. |
| Account access needs lifecycle review | The directory includes employment status, last-access, and end-date information. | Without regular reviews and timely offboarding, access may remain active after it is no longer needed. |

## Recommendations

1. **Apply least privilege:** Replace broad shared-drive administration with role-based access controls. Limit payroll and payment records to authorized finance staff.
2. **Review accounts regularly:** Reconcile account permissions against job responsibilities, employment status, and contract end dates. Remove unnecessary access.
3. **Strengthen offboarding:** Use a documented checklist to promptly disable accounts and revoke credentials when employment or contracts end.
4. **Protect sensitive accounts:** Require multifactor authentication for administrative and other sensitive access.
5. **Monitor sensitive changes:** Review payroll and payment events using account, timestamp, device, network, and authorization context. Confirm events against approved business activity before drawing conclusions.

## Result

The records indicate that administrative access is broader than necessary and that a payroll-related event merits contextual review. Role-based permissions, account lifecycle controls, multifactor authentication, and focused audit review would reduce exposure while supporting investigation of sensitive activity.

## Key Takeaway

Access control is most effective when permissions match job duties, accounts are maintained throughout the employment lifecycle, and sensitive activity is reviewed with enough context to distinguish expected work from events that need further investigation.

## Supporting Materials

- [Access-control worksheet](./Access-control-worksheet.pdf)
- [Employee directory exercise](./Accounting-exercise-employee-directory.pdf)
- [Event log exercise](./Accounting-exercise-event-log.pdf)
