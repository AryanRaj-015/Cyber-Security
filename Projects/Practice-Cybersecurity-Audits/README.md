# Activity: Security Audit and Risk Assessment

- **Course:** Google Cybersecurity Certificate - Course 2 (Play It Safe: Manage Security Risks)
- **Platform:** Google Skills
- **Category:** Security Audits, Controls, and Compliance
- **Materials reviewed:** Audit scope and risk assessment, controls checklist, and completed analysis

## Objective

Assess the security posture of the Botium Toys course scenario by reviewing its assets, existing controls, and compliance practices. Identify gaps and prioritize recommendations that reduce risk to company and customer data.

## Scenario

Botium Toys operates retail, e-commerce, and warehouse services. Its IT-managed assets include employee devices, internal networks, customer and business data, software, and legacy systems. The audit covers the full security program, including assets, controls, and compliance practices.

## Method

1. Reviewed the audit scope, goals, asset inventory, and risk assessment.
2. Evaluated the controls and compliance checklist against the scenario evidence.
3. Distinguished controls already in place from gaps requiring remediation.
4. Used the report's stated risk rating and identified weaknesses to prioritize improvements.

## Findings

| Area | Finding | Risk |
|---|---|---|
| Access and data protection | Employees have broad access to internal data, including customer information; least privilege and separation of duties are not established. Encryption is not in use for sensitive data. | Unnecessary access increases exposure of personal and payment information and creates opportunities for misuse. |
| Authentication | Password requirements are weak, and there is no centralized password-management system. | Weak or reused credentials can make unauthorized account access more likely. |
| Detection and recovery | The scenario identifies no intrusion detection system, critical-data backups, or disaster-recovery plan. | Security incidents may go undetected, and recovery or business continuity may be impaired. |
| Asset maintenance | Legacy systems are monitored, but maintenance is not scheduled consistently and intervention procedures are unclear. | Unmaintained systems may retain weaknesses and be harder to support during an incident. |
| Existing safeguards | The report notes a firewall, monitored antivirus, physical locks, CCTV, fire detection, data-integrity controls, and an EU breach-notification plan. | These controls provide useful protection, but do not compensate for the identified gaps. |

The course report assigns an overall risk score of **8/10**, describing the risk as fairly high.

## Recommendations

1. **Limit access:** Apply least privilege and separation of duties, especially for customer and payment data.
2. **Protect sensitive data:** Classify and inventory assets, then apply encryption and appropriate data-handling controls.
3. **Strengthen authentication:** Adopt a stronger password policy and centralized password-management practices.
4. **Improve detection and recovery:** Add intrusion detection, maintain tested backups, and document a disaster-recovery plan.
5. **Maintain legacy systems:** Establish regular review and maintenance schedules with clear intervention procedures.
6. **Track compliance gaps:** Map remediation to applicable PCI DSS, GDPR, and SOC control expectations, and validate progress with responsible stakeholders.

## Result

The assessment found a high-risk security posture driven by broad access, limited protection of sensitive data, and gaps in detection and recovery. Prioritizing access controls, encryption, authentication, and resilience would reduce the most significant exposures identified in the course scenario.

## Key Takeaway

A useful security audit starts with a clear scope and asset inventory, evaluates controls against evidence, and turns gaps into prioritized, actionable improvements.

## Supporting Materials

- [Audit scope, goals, and risk assessment](./Botium-Toys-Scope-goals-and-risk-assessment-report.pdf)
- [Security audit practice checklist](./Practice-Security-Audits.pdf)
- [Completed controls and compliance analysis](./Answers-of-Practice-Security-Audits.pdf)
