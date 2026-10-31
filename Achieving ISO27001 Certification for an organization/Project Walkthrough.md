# Project Walkthrough

This walkthrough documents how I approached developing an Information Security Management System (ISMS) for Stark Industries’ SaaS marketing platform, using ISO/IEC 27001:2022 as a reference.

For each stage, I explain the objective, the work I completed, and the reasoning behind my decisions. Supporting documents show how I applied the requirements to the case study, with further work identified where needed.

## Project Context

This is a guided portfolio project focused on ISMS development and certification preparation. References to Clauses 4–10 connect the project activities to the standard without reproducing its requirement text.

The work is based on the supplied company scenario. It does not represent a certification audit or an organisation that has achieved certification.

## Table of Contents

- [Clause 4 — Context of the Organisation](#clause-4--context-of-the-organisation)
- Clause 5 — Leadership *(forthcoming)*
- Clause 6 — Planning *(forthcoming)*
- Clause 7 — Support *(forthcoming)*
- Clause 8 — Operation *(forthcoming)*
- Clause 9 — Performance Evaluation *(forthcoming)*
- Clause 10 — Improvement *(forthcoming)*

## Clause 4 — Context of the Organisation

### Objective

Understand Stark Industries’ business context, identify relevant interested parties and their requirements, and define the scope of the ISMS.

### What I Did

I started by considering how Stark Industries operates: a small team delivering a SaaS marketing platform on AWS, with a limited budget and customers who may require ISO 27001 certification before procurement. These factors helped establish the business reasons for the ISMS and the resource constraints that would affect its implementation.

I documented this in the ISMS Scope document, alongside the relevant interested parties and their roles and expectations. The document identifies confidentiality, integrity, and availability as objectives for the platform’s information security. Its organisational context and stakeholder sections support Clauses 4.1 and 4.2.

For Clause 4.3, I defined the scope to include the platform’s design, development, deployment, and maintenance. This covers the personnel, processes, information assets, development environments, AWS production systems, internal tools, and third-party services involved in delivering the platform. I also documented the AWS shared responsibility model, including Stark Industries’ responsibility for securing configurations, access, and applications.

The document establishes the ISMS boundaries and provides a basis for risk assessment and control selection. It supports the establishment of the ISMS under Clause 4.4, while evidence of implementation, maintenance, and continual improvement will be developed through the remaining project stages.

### Deliverable

- [Clause 4 — ISMS Scope Document](./Clause_4_Scope.pdf)

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

- [Information Security Policy](./Clause5__InfoSec_Policy.pdf)
- [ISMS Roles and Responsibilities](./Clause5_Roles_Responsibilities.pdf)

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

- [Asset Register, Risk Assessment and Statement of Applicability](./Stark_Industries_Assets_Risk_Assessment_SoA_Completed.xlsx)
- [Risk Assessment Methodology](./Clause6__Risk%20Assessment_6_1_2.pdf)
- [Risk Treatment Process and Plan Framework](./Clause6__Risk%20Treatment%20Process%20and%20Plan_6_1_3.pdf)
- [Information Security Objectives](./Clause6_ISMS_Objectives_6_2.pdf)

<details>
<summary>Supporting policies</summary>

- [Asset Management and Data Classification](./Policy_Asset%20Management%20%26%20Data%20Classification.pdf)
- [Access Control](./Policy_Access%20Control%20Policy.pdf)
- [Secure Development](./Policy_Abed_Documents_Secure%20Development%20Policy%20%28SDLC%29.pdf)
- [Cryptography](./Policy_Cryptography%20Policy.pdf)
- [Acceptable Use](./Policy_Acceptable%20Use%20Policy.pdf)
- [Business Continuity and Disaster Recovery](./Policy_Business%20Continuity%20%26%20Disaster%20Recovery%20Policy.pdf)
- [Data Retention and Disposal](./Policy_Data%20Retention%20%26%20Disposal%20Policy.pdf)
- [Incident Management](./Policy_Incident%20Management%20Policy.pdf)
- [Monitoring and Logging](./Policy_Monitoring%20%26%20Logging%20Policy.pdf)
- [Supplier Management](./Policy_Supplier_Management_Policy.pdf)
- [Training and Awareness](./Policy_Training%20%26%20Awareness%20Policy.pdf)

</details>

### Further Work

- Resolve flagged SoA exclusions and record control implementation status and evidence.
- Agree treatment deadlines and resources, confirm risk ownership, and obtain treatment plan approval and residual risk acceptance.
- Implement and test the controls, then reassess residual risk using the results.
- Complete objective action plans and document ISMS risks, opportunities, and planned changes.

### Lesson Learned

A policy establishes expectations, but it does not demonstrate that a control is effective. Linking assets, risks, controls, owners, and validation checks made the treatment decisions easier to explain and review.
