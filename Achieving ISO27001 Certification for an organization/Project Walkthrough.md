# Project Walkthrough

This walkthrough documents how I approached developing an Information Security Management System (ISMS) for Stark Industries’ SaaS marketing platform, using ISO/IEC 27001:2022 as a reference.

For each stage, I explain the objective, the work I completed, and the reasoning behind my decisions. Supporting documents show how I applied the requirements to the case study, with further work identified where needed.

## Project Context

This is a simulated portfolio project focused on ISMS development and ISO27001 certification preparation. References to Clauses 4–10 of the official ISO document were made to complete this project.

Please note that the work is based on the supplied company scenario. It does not represent a certification audit or an organisation that has achieved certification.


## Table of Contents

- [Clause 4 — Context of the Organisation](#clause-4--context-of-the-organisation)
- [Clause 5 — Leadership](#clause-5--leadership)
- [Clause 6 — Planning](#clause-6--planning)
- [Clause 7 — Support](#clause-7--support)
- [Clause 8 — Operation](#clause-8--operation)
- [Clause 9 — Performance Evaluation](#clause-9--performance-evaluation)
- [Clause 10 — Improvement](#clause-10--improvement)

## Clause 4 — Context of the Organisation

### Objective

Understand Stark Industries’ business context, identify relevant interested parties and their requirements, and define the scope of the ISMS.

### What I Did

I started by considering how Stark Industries operates: a small team delivering a SaaS marketing platform on AWS, with a limited budget and customers who may require ISO 27001 certification before procurement. These factors helped establish the business reasons for the ISMS and the resource constraints that would affect its implementation.

I documented this in the ISMS Scope document, alongside the relevant interested parties and their roles and expectations. The document identifies confidentiality, integrity, and availability as objectives for the platform’s information security. Its organisational context and stakeholder sections support Clauses 4.1 and 4.2.

For Clause 4.3, I defined the scope to include the platform’s design, development, deployment, and maintenance. This covers the personnel, processes, information assets, development environments, AWS production systems, internal tools, and third-party services involved in delivering the platform. I also documented the AWS shared responsibility model, including Stark Industries’ responsibility for securing configurations, access, and applications.

The document establishes the ISMS boundaries and provides a basis for risk assessment and control selection. It supports the establishment of the ISMS under Clause 4.4, while evidence of implementation, maintenance, and continual improvement will be developed through the remaining project stages.

### Deliverable

- [Clause 4 — ISMS Scope Document](./Documents/Clause_4_Scope.pdf)

### Further Work

- Document relevant external issues and confirm applicable legal, regulatory, and contractual requirements.
- Define each interested party’s information security requirements and specify which will be addressed through the ISMS.
- Complete the document’s approval and review details.
- Document the ISMS processes, their interactions, and evidence of implementation.


## Clause 5 — Leadership

### Objective

Define leadership accountability for the ISMS, establish the Information Security Policy, and assign information security responsibilities and authorities.

### What I Did

With the ISMS scope defined, I focused on who would lead it and how information security would support the business. I developed two documents: the Information Security Policy and the ISMS Roles and Responsibilities document.

For Clause 5.1, I documented the CEO’s accountability for the ISMS, including providing resources, approving the policy, and aligning information security with business objectives. The policy also sets out leadership’s commitment to integrating the ISMS into business processes and supporting continual improvement. These commitments establish the expected role of management, with evidence of leadership actions still to be recorded.

For Clause 5.2, I connected the policy to Stark Industries’ SaaS operations and its objectives for customer growth, reliable service, and customer trust. The policy addresses confidentiality, integrity, and availability through objectives covering secure deployment, system availability, data integrity, prevention of unauthorised access, and security awareness. It also includes commitments to meeting applicable requirements and continually improving the ISMS through risk assessment, control monitoring, internal audits, and management reviews.

For Clause 5.3, I assigned responsibilities across management, GRC, security operations, infrastructure, and software development. The Information Security Manager is responsible for ISMS conformity and reporting performance to top management. The GRC Analyst maintains ISMS documentation and tracks corrective actions, while technical roles cover threat detection, vulnerability management, AWS security, backup and recovery, and the secure software development lifecycle (SSDLC).

I also clarified the distinction between responsibility and accountability: the CEO delegates day-to-day ISMS management to the Information Security Manager but retains overall accountability. Employees and contractors have defined responsibilities for following policies, protecting information, and reporting security incidents.

### Deliverables

- [Information Security Policy](./Documents/Clause5__InfoSec_Policy.pdf)
- [ISMS Roles and Responsibilities](./Documents/Clause5_Roles_Responsibilities.pdf)

### Further Work

- Complete policy approval, version control, and review details.
- Record how the policy and assigned responsibilities are communicated, and how the policy is made available to relevant interested parties.
- Retain evidence of leadership commitment, including resource allocation, management decisions, and ISMS performance reporting.
- Define measures, targets, and owners for the information security objectives, and validate applicable legal, regulatory, and contractual requirements.


## Clause 6 — Planning

### Objective

Assess information security risks affecting the SaaS platform, select appropriate controls, and establish measurable objectives for the ISMS.

### What I Did

I began the risk assessment but paused at asset identification. To assess the risks meaningfully, I first needed to establish what required protection, who owned it, and its confidentiality, integrity, and availability requirements.

I developed the Asset Management and Data Classification Policy and recorded five assets: the source code repository, AWS production environment, CI/CD pipeline, developer laptop, and application data. The register connects each asset to its owner, classification, business purpose, threats, and vulnerabilities.

For Clause 6.1.2, I applied a documented likelihood × impact methodology with defined risk acceptance criteria. The initial assessment identified three High and two Medium risks. This provided a basis for prioritising treatment rather than selecting controls without reference to the organisation’s exposure.

For Clause 6.1.3, I selected controls for each risk and linked them to supporting policies. For example, the source code risk is addressed through restricted access, MFA, privileged access reviews, and logging. Pipeline risks are addressed through secrets management, approval controls, and security testing.

I populated the Statement of Applicability with decisions and justifications for all 93 Annex A controls, referencing relevant policies and identifying gaps. Where the training example’s exclusions conflicted with the project’s assets or policies, I retained the decision for traceability and flagged it for review.

I also assigned proposed risk owners based on the asset register and documented projected residual risk. These estimates assume the controls are implemented and effective; validation checks are recorded against each risk. Four risks project to Medium and one to Low, with implementation and risk owner acceptance still pending.

For Clause 6.2, I defined objectives with targets, owners, measurement methods, and review frequencies. These include secure code review for every production release, monthly SaaS availability of at least 99.9%, and completion of security awareness training by all staff.

Together, these documents connect the assets, assessed risks, proposed controls, responsibilities, and intended outcomes.

### Deliverables

- [Asset Register, Risk Assessment and Statement of Applicability](./Documents/Stark_Industries_Assets_Risk_Assessment_SoA.pdf)
- [Risk Assessment Methodology](./Documents/Clause6__Risk%20Assessment_6_1_2.pdf)
- [Risk Treatment Process and Plan Framework](./Documents/Clause6__Risk%20Treatment%20Process%20and%20Plan_6_1_3.pdf)
- [Information Security Objectives](./Documents/Clause6_ISMS_Objectives_6_2.pdf)

<details>
<summary>Supporting policies</summary>

- [Asset Management and Data Classification](./Documents/Policy_Asset%20Management%20%26%20Data%20Classification.pdf)
- [Access Control](./Documents/Policy_Access%20Control%20Policy.pdf)
- [Secure Development](./Documents/Policy_Lolly_Documents_Secure%20Development%20Policy%20%28SDLC%29.pdf)
- [Cryptography](./Documents/Policy_Cryptography%20Policy.pdf)
- [Acceptable Use](./Documents/Policy_Acceptable%20Use%20Policy.pdf)
- [Business Continuity and Disaster Recovery](./Documents/Policy_Business%20Continuity%20%26%20Disaster%20Recovery%20Policy.pdf)
- [Data Retention and Disposal](./Documents/Policy_Data%20Retention%20%26%20Disposal%20Policy.pdf)
- [Incident Management](./Documents/Policy_Incident%20Management%20Policy.pdf)
- [Monitoring and Logging](./Documents/Policy_Monitoring%20%26%20Logging%20Policy.pdf)
- [Supplier Management](./Documents/Policy_Supplier_Management_Policy.pdf)
- [Training and Awareness](./Documents/Policy_Training%20%26%20Awareness%20Policy.pdf)

</details>

### Further Work

- Resolve flagged SoA exclusions and record control implementation status and evidence.
- Agree treatment deadlines and resources, confirm risk ownership, and obtain treatment plan approval and residual risk acceptance.
- Implement and test the controls, then reassess residual risk using the results.
- Complete objective action plans and document ISMS risks, opportunities, and planned changes.

### Lesson Learned

A policy establishes expectations, but it does not demonstrate that a control is effective. Linking assets, risks, controls, owners, and validation checks made the treatment decisions easier to explain and review.



## Clause 7 — Support

### Objective

Identify the competence needed to operate the ISMS and plan how staff will develop and maintain the knowledge and skills required for their roles.

### What I Did

With responsibilities already defined, I considered what each person would need to perform them effectively. I created a competence register for the six project roles, recording required competencies, evidence of competence, training, and review dates.

For Clause 7.2, I matched competencies to specific responsibilities. The developer’s entry covers secure coding and threat modelling, while the Security Analyst’s covers security monitoring and incident response. For the GRC Analyst, I included risk assessment and compliance reporting, supported by work such as risk logs, the Statement of Applicability, and audits.

I also documented how competence would be maintained: annual reviews, reassessment following significant changes, and targeted training or reassignment where gaps are identified. The entries are part of the hypothetical scenario; supporting evidence and review dates still need to be completed.

For Clause 7.3, I connected this work to the existing ISMS objective of achieving 100% staff completion of security awareness training. The objective provides a measurable target, while the competence register identifies role-specific training needs. Attendance would be tracked alongside checks that staff understand their security responsibilities.

### Deliverable

- [Competence Management and Awareness Records](./Documents/Clause7_Competence_Records_7_2.pdf)

### Further Work

- Complete review dates and attach evidence such as qualifications, training records, and practical assessments.
- Assess whether training improves performance, using exercises relevant to each role.
- Check staff awareness of the Information Security Policy, their contribution to the ISMS, and the consequences of nonconformity.
- Document resource needs, communication arrangements, and document controls for the remaining areas of Clause 7.

### Lesson Learned

Training completion is only one part of competence. I also need evidence that a person can apply the knowledge to their responsibilities, whether that means investigating an incident, reviewing code, or assessing risk.


## Clause 8 — Operation

### Objective

Create a clear way to track control implementation and the evidence needed to demonstrate that risk treatment actions are being carried out.

### What I Did

After selecting controls in Clause 6, I needed a way to follow their implementation. I created a Control Evidence Tracker covering the 63 Annex A controls currently marked as applicable in the Statement of Applicability.

For each control, I included fields for implementation status, evidence type, evidence location, responsible owner, verification date, and comments. This creates a consistent record of what needs to be demonstrated, who will provide it, and where it can be reviewed.

The tracker supports operational planning and control under Clause 8.1 by providing a structure for following up on implementation. For example, access control evidence could include approved access requests and review records, while backup evidence could include restoration test results. These records would help connect the policy requirements to activities performed in practice.

At this stage, the controls are marked as Planned. Evidence references, owners, and verification dates remain to be populated. I kept that distinction visible so the tracker reflects the actual stage of the project.

### Deliverable

- [Control Evidence Tracker](./Documents/Stark_Industries_Control_Evidence_Tracker.pdf)

### Further Work

- Assign control owners and define the evidence and verification criteria for each control.
- Populate evidence locations and verification dates as implementation progresses.
- Link evidence to the risk treatment actions and record implementation results for Clause 8.3.
- Reassess risks at planned intervals and following significant changes under Clause 8.2.
- Update the tracker when the flagged SoA applicability decisions are resolved.

### Lesson Learned

Evidence needs to be planned alongside implementation. Defining what I expect to see for each control makes it easier to identify gaps and distinguish a documented policy from a control that is operating.


## Clause 9 — Performance Evaluation

### Objective

Define how ISMS performance would be measured, independently assessed, and reviewed by management.

### What I Did

With the evidence tracker in place, I focused on how to judge whether the ISMS was achieving its objectives.

For Clause 9.1, I defined monitoring responsibilities, frequencies, and evaluation criteria for measures including training completion, backup testing, access reviews, and vulnerability remediation. This provides a basis for identifying trends and prioritising action.

For Clause 9.2, I developed an internal audit programme covering the full ISMS scope, with defined criteria, methods, reporting timelines, and corrective action follow-up. I prepared the programme for the exercise; audits would require competent, impartial auditors independent of the activities being assessed.

For Clause 9.3, I created a management review procedure, agenda, and minutes template to bring together performance results, audit findings, risk updates, and resource needs. The template records decisions, action owners, and deadlines to support follow-through.

These documents establish the evaluation process. KPI results, audit findings, and management decisions remain to be recorded.

### Deliverables

- [Monitoring and Evaluation Procedure](./Documents/Clause9_monitoring_analyis_kpis_9_1.pdf)
- [Internal Audit Programme](./Documents/Clause9_internal_audit_plan_9_2.pdf)
- [Management Review Procedure](./Documents/Clause9_managment_review_plan_9_3.pdf)
- [Management Review Agenda and Minutes](./Documents/Stark_ISMS_Management_Meeting_Agenda_Minutes.pdf)

### Further Work

- Align monitoring criteria with the Clause 6 objectives and collect performance results.
- Schedule independent audits and track findings through corrective action.
- Conduct management reviews and follow up on assigned decisions and actions.

### Lesson Learned

I approached performance evaluation as a decision-making process: measurements identify concerns, audits examine the evidence, and management reviews determine the response.


## Clause 10 — Improvement

### Objective

Establish a way to record nonconformities, assign responsibility, and follow corrective actions through to verified resolution.

### What I Did

After defining how performance would be evaluated in Clause 9, I focused on what should happen when a review identifies a gap.

I created a Nonconformity Log with fields for the control name, owner, finding description, finding date, resolution date, status, and comments. This provides a central record for assigning accountability and tracking outstanding issues.

For Clause 10.2, the log provides the starting point for managing nonconformities and corrective actions. I would use it to capture findings from audits, control reviews, or incidents, then document the immediate correction, investigate the root cause, and track action to prevent recurrence. Closure would depend on evidence that the action was effective.

For Clause 10.1, reviewing recurring findings and overdue actions would help identify improvements to policies, processes, training, or controls. These insights would feed back into management review and ISMS planning.

The current deliverable is an unpopulated template. It establishes the tracking structure; completed corrective actions and effectiveness checks remain to be demonstrated.

### Deliverable

- [Nonconformity Log](./Documents/Stark_ISMS_NonConformity_Log.pdf)

### Further Work

- Add fields for the requirement not met, supporting evidence, root cause, correction, corrective action, and target completion date.
- Record effectiveness checks, closure evidence, and approval before closing findings.
- Review recurring issues and overdue actions during management reviews.

### Lesson Learned

Resolving an individual issue is only part of the work. I also need to understand why it happened and verify that the corrective action addresses the cause.
