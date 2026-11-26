# Activity: Data Leak and Least-Privilege Review

- **Course:** Google Cybersecurity Certificate - Course 5 (Assets, Threats, and Vulnerabilities)
- **Platform:** Google Skills
- **Category:** Data Protection and Access Control
- **Materials reviewed:** Data leak worksheet and completed analysis

## Objective

Analyze how a mistaken external share exposed internal company information, identify the access-control weaknesses that contributed to the incident, and recommend improvements based on least privilege.

## Scenario

A sales manager shared an internal folder with the team for a meeting but did not revoke access afterward. The folder contained information about an unannounced product, customer analytics, and promotional materials. Later, a sales representative intended to share approved promotional materials with a business partner but accidentally shared the internal-folder link. The partner then posted that link publicly, believing it contained the approved materials.

## Method

1. Traced how access to the internal folder was granted and left active.
2. Identified how the wrong link was selected and shared with an external recipient.
3. Applied the principle of least privilege and the worksheet's NIST SP 800-53 AC-6 reference.
4. Developed preventive recommendations for permissions, link expiry, and access review.

## Findings

| Contributing factor | Evidence from the scenario | Risk |
|---|---|---|
| Access remained active beyond the meeting | The manager did not revoke the team's access to the internal folder. | People may retain access after the business need ends. |
| Internal and approved materials were easy to confuse | The representative intended to share promotional materials but sent the internal-folder link instead. | A simple sharing mistake can expose confidential data externally. |
| External access was not sufficiently restricted | The partner could open and publicly post the shared link. | Unannounced product information and customer analytics could be disclosed. |

## Recommendations

1. Restrict sensitive folders to authorized users and roles, granting only the access needed for a specific task.
2. Use separate, clearly labeled folders for internal materials and approved external content.
3. Set shared-link permissions to internal-only by default; require approval for external sharing.
4. Apply expiration dates and promptly revoke temporary access when meetings or projects end.
5. Maintain access logs and regularly audit permissions for sensitive information.
6. Train staff to verify recipient and link permissions before sharing files externally.

## Result

The incident was enabled by lingering access and an incorrect link being shared externally. Least-privilege permissions, time-limited sharing, clear separation of internal and approved materials, and routine access reviews would reduce the chance and impact of a similar mistake.

## Key Takeaway

Least privilege includes managing how long access lasts and who can receive a shared link. Clear sharing boundaries and timely revocation help prevent accidental disclosure.

## Supporting Materials

- [Data leak worksheet](./Practice-Data-leak-worksheet.pdf)
- [My completed analysis](./My-answer-Data-leak-worksheet.pdf)
