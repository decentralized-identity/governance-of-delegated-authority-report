# Governance of Delegated Authority Problem Space Report v0.1 Editor's Draft

**Specification Status:** Pre-Draft

**Latest Draft:**
[identity.foundation/delegated-authority-report](https://identity.foundation/delegated-authority-report)

**Ratified Versions:**

**Editors:**

* Alan Karp (@alanhkarp)

**Authors:**

* Debbie Bucci

**Participate:**
~ [GitHub repo](https://github.com/decentralized-identity/governance-of-delegated-authority-report)
~ [File a bug](https://github.com/decentralized-identity/governance-of-delegated-authority-report/issues)
~ [Commit history](https://github.com/decentralized-identity/governance-of-delegated-authority-report/commits/main)
~ [Working Group](https://identity.foundation/working-groups/trusted-agents.html)

Except where otherwise noted, this work by the [Decentralized Identity Foundation](https://identity.foundation/) is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0).

## Abstract

add text here

## Status of This Document

This is a draft specification being developed within the
[Decentralized Identity Foundation](https://identity.foundation) (DIF).
Design
work is ongoing, and participants are
encouraged to open issues or otherwise contribute at [the DIF-hosted github
repository](https://github.com/decentralized-identity/governance-of-delegated-authority-report),
whether as input to stable versions or as recommendations for future versions.

## Introduction

### The Emergence of AI-Mediated Decision and Action Systems

Automated systems are increasingly embedded in operational pipelines where decisions are prepared, recommended, or executed with limited human involvement.
These systems retrieve and synthesize information, trigger downstream actions, invoke services on behalf of users or organizations, and propagate instructions across system and organizational boundaries.
As deployment has expanded, automated components operate as participants within broader sociotechnical processes rather than as isolated tools.

### Why governance of authority is distinct from AI functionality or model accuracy

Discussion of automated systems commonly focuses on **functionality** — whether a system can perform a task — or on performance — accuracy, bias, or explainability.
These considerations do not address a distinct governance issue — **authority**.
Functionality describes what a system is able to do; authority describes the legitimate right to act.
A system may perform a task accurately while operating outside the scope of its granted authority.
Conversely, a system operating within its authorized scope may still produce undesirable outcomes if that scope was poorly defined or insufficiently constrained.
Governance of authority addresses the structural conditions under which automated systems are permitted to act.

Existing governance approaches often assume that the **scope of authority** required for a task can be defined *in advance*.
In distributed automated environments, however, actions may occur across multiple services, organizational boundaries, and execution layers where the full sequence of operational steps cannot always be anticipated at design time.
Governance frameworks must therefore account for conditions in which authority boundaries, delegation scope, and enforcement mechanisms must remain explicit and verifiable even as automated processes operate dynamically.
The challenge is not the functionality of automated systems but ensuring that delegation of authority remains **accountable, constrained,** and **consistent** with the intent of the principal that granted it.

## Authority in Sociotechnical Systems

### Sources of authority (human, institutional, legal)

A person may hold authority by virtue of a role, contractual relationship, legal instrument, or legally recognized relationship, such as a parent acting on behalf of a child.

An organization may hold authority by statute, agreement, or the terms under which it operates within a regulated domain.
These sources form the *foundation* from which delegated authority derives.
No automated system generates authority of its own; it can only exercise authority granted by a principal who holds, or has itself been delegated, the relevant right to act.
The **provenance** of authority determines the conditions under which it is legitimate, the constraints that attach to it, and the obligations that arise when it is exercised.

### Representation of authority in technical systems

When authority is exercised through automated systems, it must be represented in forms those systems can process.
Credentials, tokens, signed assertions, and access control configurations are common mechanisms for expressing authority technically.
These representations necessarily reduce the richer legal and organizational structures from which that authority derives.
A credential may assert that a system is authorized to perform a class of actions without capturing the *conditions, purposes, or limitations* governing that authorization in its originating context.
The gap between the scope of authority as understood by its originating principal and its representation within a technical system is a persistent governance challenge.
Where that gap is significant, systems may act in ways technically consistent with their authorization while departing from the intent of the original grant.

### Distinguishing capability from authority

The distinction between **capability** and **authority** is analytically important but frequently obscured in practice.
A system with the technical means to perform an action may do so in the absence of explicit controls, regardless of whether authority for that action has been granted.
In human governance contexts, this distinction is maintained through rules, professional norms, and the accountability of individuals who understand that the capacity to act does not constitute permission to act.
In automated systems, the distinction must be maintained through *explicit design*: access controls, authorization checks, scope constraints, and enforcement mechanisms.
Where these mechanisms are absent, incomplete, or inconsistently applied, capability and authority collapse, and systems act to the limits of what they can do rather than what they are permitted to do.

## Delegation of Authority

### Delegation relationships and chains of responsibility

Delegation is the process by which a principal permits another party to act on its behalf.
In operational environments, authority is rarely exercised solely by the entity that originally holds it.
Instead, it is delegated so that tasks and decisions can be performed by others within an organizational or technical system.

Delegation establishes **chains of responsibility**.
Each participant exercises authority that originates elsewhere and is bounded by the conditions under which it was granted.
The legitimacy of any delegated action depends on the integrity of this chain.
Where the delegation chain between the acting entity and the original principal cannot be reconstructed, the basis for the authority being exercised becomes unclear.
In complex sociotechnical environments, delegation chains may extend across multiple actors, services, organizations, or automated components.
Maintaining continuity of authority across these relationships helps ensure that actions performed within a system remain connected to their originating source of authority.

### Attenuation and scope limitation

Delegated authority is rarely equivalent to the authority held by the delegating principal.
Delegation is typically constrained so that the delegated actor exercises only a limited subset of that authority — a process referred to as attenuation.

Attenuation limits the *scope* within which delegated authority may be exercised.
The delegated actor may be permitted to perform specific actions, operate within defined roles, or act only under particular conditions.
These constraints reduce the risk that delegated actors — whether human or automated — exercise authority beyond the intent of the grant.
Governance frameworks should promote the principle that delegated authority be limited to the **minimum scope necessary** for the intended purpose.

Without clear scope limitations, authority may expand as it propagates through operational systems.
Governance mechanisms must therefore ensure that the limits attached to delegated authority remain visible and enforceable as authority moves across technical and organizational boundaries.

In some cases, a delegation may not satisfy all applicable policy constraints.
Where the delegator is aware of such a limitation, communicating the reason to the receiving system allows the verifier to make an informed judgment about whether to honor the delegation in the given context.
Governance frameworks should address how such exceptions are expressed, evaluated, and recorded.

### Duration, revocation, and termination of delegated authority

Delegated authority is bounded in time or circumstance.
A delegation may apply for a defined duration, for completion of a specific task, or until particular conditions are met.
Effective governance therefore requires mechanisms that define not only how authority is granted but how it expires or is withdrawn.

**Revocation** is particularly important when authority propagates through distributed systems.
When a delegation is withdrawn or reaches its termination point, the component responsible for evaluating whether a request is authorized must recognize that change and prevent further actions under the previously granted authority.
Constraining scope, defining duration, and enabling revocation ensures that delegated actions remain aligned with the intent of the granting principal.

## Agents Operating Under Delegated Authority

### Automated systems as decision-support participants

Automated systems participate in decision and execution pipelines in a variety of operational roles.
At one end, a system may provide analysis or recommendations that a human actor evaluates before action is taken.
At the other, a system may execute actions directly, with human involvement limited to initial configuration.
Between these poles are intermediate arrangements in which automated components *prepare, filter, prioritize, or route decisions* in ways that **shape outcomes** without formally making them.

Understanding the governance implications of delegated authority requires clarity about which role an automated system occupies.
Systems that provide advice influence decisions but do not exercise authority.
Systems that execute actions operate as delegates acting under granted authority.
The distinction between advisory participation and operational execution is therefore central to determining the appropriate forms of governance and accountability.

### Agents acting under delegated authority

Where an automated system is authorized to take actions on behalf of a principal, it operates as a delegate in the sense described in Section 3.
The authority it exercises is derived from a grant made by a principal who holds, or has itself been delegated, the relevant right to act.

The **scope** of the system’s authority is bounded by the **terms** of the delegation.
Actions outside that scope are not authorized, regardless of whether the system is technically capable of performing them.
Conditions attached to the delegation — including purpose limitations, contextual constraints, or policy requirements — apply to the system’s actions in the same way they would apply to a human delegate in an equivalent role.

Where automated agents operate **across multiple** technical systems, the delegated authority under which they act must remain recognizable and enforceable throughout the operational chain.
The automated nature of the actor does not alter the governance structure but affects the mechanisms through which it must be implemented and enforced.

### Limits of machine autonomy within governance frameworks

Governance frameworks historically assumed delegates would be *human* actors capable of interpreting ambiguity, seeking clarification, or declining to act when the limits of their authority were unclear.
Automated systems do not replicate this form of judgment; they operate within the rules and parameters provided and act to the extent those rules permit.

This has two implications for governance.
First, **explicit specification** of authority scope, conditions, and limits becomes more *consequential*.
Ambiguities that a human delegate might resolve through judgment may result in unintended actions when exercised by an automated system.
Second, automated systems must operate within **defined boundaries** that determine when autonomous action is permitted and when human oversight must be engaged.

Maintaining these boundaries ensures that automated agents remain instruments of delegated authority rather than independent decision-makers, preserving the principle that machine actions are extensions of human or institutional authority.
In some cases, operational conditions may create a need for additional authority beyond that originally granted.
Governance frameworks should ensure that any such expansion is subject to explicit review, policy constraint, and accountability.

## Authority Boundaries in Distributed Systems

### Separation of analysis, recommendation, and execution

In distributed systems, the functions of **analysis**, **recommendation**, and **execution** are often performed by different components across separate services or organizational contexts.
This separation has governance significance because each function relates differently to authority.
Analysis and recommendation influence decisions by producing information or suggesting possible actions.
Execution brings authority to bear by performing actions that may alter data, initiate transactions, or trigger downstream effects.

Governance frameworks should *reflect* this deep and consequential distinction.
Systems that analyze information or generate recommendations do not exercise authority to act.
Authority is exercised only when a system performs an operation that commits resources or changes the state of its operational environment.
Maintaining a clear boundary between *advisory* and *executive* functions helps prevent analytical outputs from being treated as authorized actions.

Where analysis and execution are performed by the same component without clear separation, the risk of *premature* or *unauthorized* action increases.
Architectural separation of these functions, combined with explicit authority controls at the point of execution, supports clearer accountability and more effective oversight.

### Controlled propagation of delegated authority across system boundaries

When delegated authority passes from one system to another, the terms of the delegation should travel with it.
Where they do not, a receiving system must have other means of determining the scope of the authority, the conditions attached to it, and the originating principal from whom it derives.

In practice, the conditions attached to a delegation are often only *partially* represented as authority moves between systems.
When a receiving system acts on an incomplete representation, it may authorize actions that extend beyond the original intent of the principal.

Effective governance therefore requires mechanisms that preserve the continuity of delegated authority across system boundaries.
Receiving systems must evaluate not only whether authority has been asserted, but whether the scope and conditions attached to it remain **applicable** to the action being requested.

### Managing authority across heterogeneous systems and organizations

Distributed environments frequently involve systems operated by different organizations and built on different technical standards.
Each organization may represent and enforce delegated authority according to its own governance policies.
When authority moves between these environments, differences in interpretation may create enforcement gaps or misunderstandings about what actions are permitted.

Managing delegated authority across heterogeneous systems requires a **shared understanding** of how authority is *expressed*, what *constraints* accompany it, and how those constraints should be *interpreted* by participating systems.
Interoperability in this context is therefore not only a technical concern but also a serious governance concern.
Systems must interpret the constraints and conditions attached to delegated authority consistently if delegation chains are to remain aligned with delegator policy across organizational and technical boundaries.
Without this shared understanding, systems may enforce the constraints and conditions attached to delegated authority inconsistently, authorizing actions that do not reflect the policy preferences of the delegator.
Identity and authorization *frameworks* that support the representation and communication of delegated authority across organizational boundaries are discussed further in the  [Implications](#implications-for-identity-and-authorization-frameworks) section.

## Provenance, Traceability, and Accountability

### Recording decision pathways

When automated systems participate in decision and execution pipelines, the pathway from an initial authority grant to a resulting action may pass through multiple components, services, and organizations.
Accountability depends on the ability to understand that pathway after the fact.

Recording decision pathways therefore requires more than documenting the final action taken.
It requires capturing the basis on which the action was authorized: what authority was asserted, under what conditions it was exercised, and at what point in the operational chain the decision to act occurred.
These records allow organizations to understand how authority was interpreted and applied at the time an action was performed.

Without such records, it may be possible to observe that an action occurred while remaining unable to determine whether it was consistent with the policy expressed in the delegations under which it was taken.
This limits the ability of principals, auditors, and affected parties to assess whether the system operated as intended and whether governance structures functioned as designed.

### Reconstruction of authority chains

Accountability requires that it be possible, after an action occurs, to reconstruct the delegation chain from which the acting system derived its authority.
Reconstruction makes visible the sequence of delegations connecting the executing system to the principal whose authority ultimately permitted the action.

This capability serves several governance purposes.
It allows the scope of authority exercised to be verified against the scope originally granted.
It identifies the principals responsible for delegation decisions that enabled the action.
And it helps reveal points in the chain where authority was asserted without adequate basis or where the policy constraints expressed in the delegation were not correctly enforced.

Reconstruction is not always straightforward.
Delegation chains may span multiple services, technical environments, or organizations, each maintaining its own records.
Governance frameworks should therefore treat the ability to trace accountability through direct delegation relationships as a design requirement rather than a retrospective aspiration.

### Non-repudiation and evidentiary considerations

Where delegated actions may be contested — whether in regulatory proceedings, contractual disputes, or internal accountability processes — it may be necessary to establish with confidence that a particular action occurred and that it was taken under a specific grant of authority.

Non-repudiation refers to the property of a record that prevents the responsible party from credibly denying that an action occurred, that the authority enabling it was granted, or that someone else performed the action.

The evidentiary value of such records depends not only on their technical integrity but also on the governance processes surrounding them: how records are generated, protected, retained, and made available for review.
Systems in which delegated authority is exercised should therefore be designed so that the provenance of authority, the decisions taken under it, and the resulting actions can be reliably demonstrated if questions later arise about their legitimacy.

## Enforcement of Authority

### Policy decision versus policy enforcement

Governance of delegated authority requires distinguishing between the expression of policy rules and the enforcement of those rules at the point of action.
Policy defines the conditions under which delegated authority may be exercised — what actions are permitted, by whom, and under what circumstances.
Authorization evaluation determines whether a specific proposed action satisfies those conditions.
Enforcement ensures that actions which do not satisfy those conditions are prevented from proceeding.
These functions are logically distinct and may be performed by different components.
Confusing them — for example, assuming that a system configured with policy rules will automatically enforce them in all operational circumstances — is a common source of governance failure.
Effective governance therefore requires that authorization evaluations be performed in relation to specific actions and that the outcome be binding on the behavior of the executing system.

### Deterministic enforcement and fail-safe behavior

Enforcement mechanisms should produce consistent, predictable outcomes.
When a system cannot verify that an action is authorized, or when applicable policy conditions are not satisfied, it must decline to proceed.
This reflects a governance requirement to prevent unauthorized action rather than allow uncertain action.

Systems that default to permitting actions when enforcement checks fail or cannot be completed invert this requirement and increase the risk that authority boundaries are breached without detection.

In the absence of a positive determination that an action is authorized, the appropriate default is to deny it.
This requirement applies equally under degraded conditions such as network outages or unavailable authorization services.
Governance frameworks should define how enforcement behaves when required checks cannot be completed, ensuring that infrastructure failures do not result in unauthorized action.
Governance frameworks should define in advance the conditions under which a delegate may decline to honor a delegation, recognizing that refusal itself carries governance implications and should not occur outside explicitly defined parameters.

### Runtime evaluation of authority in operational systems

Authority that was valid when a delegation was granted may not remain valid when an action is executed.
Delegations may be revoked, conditions may change, or prior actions may alter the scope within which authority may be exercised.

Enforcement mechanisms that evaluate authority only at system initialization or session establishment may allow actions to proceed on the basis of authority that is no longer valid.
Governance frameworks should therefore ensure that authority is evaluated at a point appropriate to the action being performed.

Evaluating authority at the time an action is executed helps ensure that delegated authority remains aligned with the current state of the system, applicable policies, and the intentions of the principal from whom it derives.

It should be noted that an unavoidable race condition exists between revocation and invocation.
A delegation may be revoked at the same moment an action is being executed under it.
Governance frameworks should address how such cases are handled, including whether in-flight actions are permitted to complete and how the outcome is recorded.

### Expression of organizational policy governing delegated authority

For enforcement to operate effectively, policies governing delegated authority must be expressed in a form operational systems can evaluate.
Organizational policy is typically articulated in natural language through governance documents, contracts, or regulatory requirements.
Translating these into operational rules requires interpretation.
Where automated systems include LLM-based components, this translation challenge is compounded.
LLM agents determine their approach to a task at runtime, meaning the permissions required may not be fully anticipatable at policy definition time.
Governance frameworks must therefore address how policy constraints can be expressed and enforced dynamically, adapting to the agent's evolving permission requirements without requiring human intervention at each step.

Where policies are **ambiguous**, translation may resolve ambiguity in ways that differ from the intent of the policy-making body.
Where policies evolve, operational rules may not be updated consistently.
Governance frameworks should therefore establish clear processes for translating organizational policy into enforceable system rules and ensuring those rules remain aligned with the policy they implement.
Not all policy constraints are equally enforceable in practice.
Some are better expressed as preferences that participants are expected to honor, with enforcement reserved for constraints where violations carry significant governance consequences.

### Separation of decision and enforcement in distributed systems

In distributed environments, policy decision and policy enforcement are often performed by separate components.
A decision component evaluates whether an action is authorized under applicable authority and policy conditions.
An enforcement component applies that outcome by permitting or blocking the action.

This separation allows policy logic to be maintained centrally while enforcement occurs close to the point of execution.
It also introduces dependencies: if an enforcement component cannot obtain a decision, or fails to apply the decision correctly, policy will not be enforced reliably.

Governance of distributed enforcement therefore requires attention to the integrity of the relationship between decision and enforcement components, including system behavior when that relationship is interrupted.

Across delegated authority systems, the critical control point is not the issuance of authority but its validation at the moment of action.
Delegation chains, credentials, and authorization artifacts provide necessary inputs to enforcement decisions, but do not substitute for runtime validation.
A valid delegation does not, by itself, confirm that a requested action is appropriate under current conditions.

Enforcement mechanisms must produce a deterministic allow or deny outcome immediately prior to execution, based on evaluation of the current authority state, including current context, constraints, and policy conditions.
Where that evaluation cannot be completed conclusively, fail-closed behavior is the appropriate default.

## Risks in Delegated Authority Systems

### Redelegation and uncontrolled propagation of authority

When a delegate is permitted to redelegate the authority it holds, the original principal loses direct control over how far that authority propagates and to whom it is extended.
Each act of redelegation introduces a new participant in the authority chain whose relationship to the original principal may be indirect or opaque.

In automated systems, redelegation may occur programmatically and at scale, often too rapidly for manual oversight to be practical.
The cumulative scope held by successive delegates can expand beyond the original grant in ways the principal did not intend and cannot readily observe.

Governance frameworks should therefore ensure that delegation mechanisms support attenuation — the ability to pass a constrained subset of held permissions to a delegate.
Where systems cannot delegate narrower permissions than those held, least-privilege enforcement becomes impractical, and principals may resort to credential sharing as a workaround, undermining both traceability and accountability.
The governance question is not whether redelegation is permitted, but how it is constrained: the conditions under which it may occur and how delegated authority remains bounded by the scope of the original grant.

### Oversharing and unintended scope grants

A related risk arises when authority is delegated at a broader scope than the task requires.
This may occur because defining precise scope is operationally inconvenient, because systems request broader authority as a precaution, or because requesting systems have little incentive to limit their own access.

When authority is granted more broadly than necessary, delegates hold permissions exceeding task requirements.
In distributed systems this risk may compound across delegation layers: each participant grants slightly more authority than required, and systems deeper in the chain hold authority substantially broader than the original principal would have sanctioned.

Governance frameworks should therefore promote the principle that delegated authority is limited to the scope necessary for the intended purpose and provide mechanisms for verifying that this limitation is observed in practice.

### Automation bias and decision acceleration risks

Where automated systems provide recommendations that human actors act upon, automation may lend those outputs an unwarranted degree of authority.
Human reviewers may be less inclined to question recommendations produced by automated systems, particularly when outputs are complex, voluminous, or generated rapidly.

Automated systems may also accelerate operational processes, reducing the time available for careful human review.
Decisions may be made and actions executed before the authority basis for those actions has been fully examined.

Together, automation bias and decision acceleration may erode effective oversight in systems where human review is formally present but practically constrained by the speed and scale of automated operations.

### Risks arising from semantic interpretation across domains

When delegated authority crosses organizational or technical boundaries, semantic interpretation remains a governance concern even where the underlying protocol defines the structure of the delegation.
Differences in terminology, governance assumptions, or operational policy may result in the same authority assertion being interpreted differently across domains.

These semantic differences may not be apparent at the time of delegation and may only become visible when an action is questioned or disputed.
In environments where automated systems act on delegated authority without individual human review, such misinterpretations may propagate silently through operational pipelines.

Governance frameworks should therefore treat semantic consistency across system boundaries as a governance requirement and establish mechanisms for identifying and resolving interpretation differences before they result in unintended actions.

### Misalignment of technical and governance trust

System-level trust does not always reflect organizational authority.
Requests that appear technically valid may originate from actors whose authority is not recognized by the receiving organization.
Governance frameworks must therefore require that technical authentication be distinguished from authorization, and that systems apply governance evaluation before acting on requests that cross organizational boundaries.

## Human Oversight in Machine-Speed Environments

### Maintaining meaningful human control

Governance frameworks for delegated authority have historically assumed that human actors remain involved in consequential decisions, either by making those decisions directly or by reviewing the actions of delegates.
Automated systems do not remove this expectation; they alter the conditions under which it must be fulfilled.

When systems operate at machine speed and scale, oversight cannot consist of reviewing each individual action.
Instead, it must be expressed through governance architecture: the design of authority boundaries, the definition of policy conditions, and the enforcement mechanisms that determine when automated action is permitted.
Meaningful human control therefore depends on the ability of principals to define the scope and limits of delegated authority in advance and to understand how those limits are enforced during operation.
Oversight shifts from moment-to-moment supervision toward governance of the systems that interpret and apply delegated authority.
Automated components may perform analysis, make recommendations, or execute defined tasks, but the authority under which they act must remain grounded in human-defined policy and institutional intent.

### Escalation and interruption mechanisms

Automated systems operating under delegated authority must include explicit mechanisms for human intervention.
Escalation mechanisms allow automated processes to defer decisions when conditions fall outside defined authority or when policy evaluation produces uncertain or conflicting results.
In such cases, the system should suspend action and route the situation for human review rather than proceed autonomously.

Interruption mechanisms provide the complementary capability: authorized human actors must be able to halt or override automated processes when oversight reveals an error, scope violation, or unforeseen consequence.
Where automated actions may propagate rapidly through interconnected systems, interruption capabilities serve as critical safeguards against uncontrolled continuation of automated behavior.

Escalation and interruption should therefore be treated as governance requirements rather than optional features.
Their presence ensures that automated execution remains subject to human judgment at critical points without requiring continuous supervision of routine activity.

### Governance of automated decision pipelines

Automated systems often participate in decision pipelines composed of multiple analytical, evaluative, and execution stages.
Governance must therefore address not only the behavior of individual components, but also the behavior of the pipeline as a whole.

A pipeline in which each component operates within its defined authority may nevertheless produce outcomes no individual component was designed to produce.
Such emergent behavior is characteristic of complex distributed systems and presents a significant governance challenge.
Actions justified at one stage may combine with decisions made elsewhere to produce outcomes that extend beyond the intent of the original delegation.

Governance frameworks should therefore treat automated pipelines as structured authority environments.
The authority and policy basis for actions at each stage must remain transparent, and the relationship between analysis, recommendation, and execution should remain observable and subject to oversight.
Maintaining visibility of delegated authority across the pipeline preserves accountability even in systems operating at machine speed.

### Observability-Based Oversight

At machine speed, oversight shifts from reviewing individual actions to observing delegation relationships, authority scopes, and automated decision flows.
Observability mechanisms allow governance actors to detect anomalies or unexpected patterns without requiring direct intervention in each action.

## Implications for Identity and Authorization Frameworks

### Identity representation for humans and agents

Governance of delegated authority depends on the ability to identify, with sufficient reliability, the parties involved in a delegation relationship.
In human governance contexts, identity is grounded in legal personhood, organizational role, and the accountability structures that attach to both.

When automated systems participate as delegates, the identity of the acting party becomes more complex.
A system may act on behalf of a user, an organization, or another system, and the identity presented at a system boundary may not fully represent that layered relationship.

Governance frameworks must therefore address how the identity of automated agents is represented, what claims an identity assertion may carry, and how the relationship between an agent’s identity and the principal it represents is expressed and verified.
Identity representations that capture only the immediate acting party, without conveying the principal on whose behalf it acts, are insufficient where accountability must be traced to a human or institutional source.

### Delegation models in distributed identity systems

Distributed identity systems provide mechanisms for asserting and verifying identity across organizational boundaries.
Extending these mechanisms to support delegated authority requires more than identity verification.
It requires the ability to represent the scope of a delegation, the conditions attached to it, and the chain of principals through which it derives.

Current identity and authorization frameworks vary in the degree to which they support *rich delegation models*.
Some provide mechanisms for expressing that a system is acting on behalf of another party; fewer convey the limits of that authorization or the policy conditions governing its exercise.

Governance frameworks should therefore assess whether identity and authorization mechanisms in use can represent the delegation relationships that operational systems rely upon, and identify gaps where richer representation is required.

### Communication of policy and delegation constraints across organizations

When delegated authority crosses an organizational boundary, the receiving organization must understand not only that authority has been granted but what conditions govern its exercise.
Communicating these conditions across organizational boundaries remains a significant governance challenge.

Policy constraints may be expressed in formats that are not interoperable between organizations, may rely on shared vocabulary that is not formally defined, or may be conveyed through documentation rather than in a form systems can evaluate directly.
As a result, receiving organizations may have an incomplete or informal understanding of the constraints attached to the authority they are asked to rely upon.

Governance frameworks should therefore require that policy and delegation constraints are communicated in a form that is explicit, evaluable by receiving systems, and consistent with the intent of the delegating principal.

### Representation of policy expectations across trust boundaries

Beyond formally stated policy, delegated authority may carry contextual expectations not fully articulated in the delegation itself.
These expectations may reflect the purpose for which authority was granted, the relationship between the parties, or norms widely understood within a domain but not formally expressed.

Such contextual dimensions are difficult to represent in machine-readable form and are frequently lost as authority crosses system and organizational boundaries.
Trust boundaries are where this loss is most likely to occur.

Governance frameworks should therefore address how expectations attached to delegated authority are preserved as authority crosses trust boundaries and should clarify the obligations of receiving organizations with respect to constraints that cannot be fully represented in the delegation artifact.

### Interoperability considerations

Effective governance of delegated authority in distributed environments depends on interoperability among the identity, authorization, and policy mechanisms used by different organizations.
Where these mechanisms are inconsistent, authority assertions may not be interpretable across boundaries, enforcement may vary across domains, and accountability gaps may arise that no single organization can resolve alone.

Interoperability in this context has both technical and governance dimensions.
Technical interoperability concerns the ability of systems to exchange and process authority assertions.
Governance interoperability concerns shared understanding of what those assertions mean, what obligations they carry, and how disputes about their interpretation are resolved.

Standards work in this area should address both dimensions, recognizing that technical interoperability without governance interoperability does not reliably preserve the integrity of delegated authority across organizational boundaries.

### Operationalizing Governance Principles

Translating governance requirements into system architecture
The governance principles discussed in this paper — authority provenance, delegation scope, policy enforcement, accountability, and human oversight — must ultimately be expressed in the **architecture** of operational systems.
This translation is not automatic.
Governance requirements articulated at the policy level do not directly specify system behavior; they must be interpreted and implemented through deliberate architectural choices.

Operational systems reflect governance intent only when that intent is clearly specified, consistently applied across components, and verified against the requirements it was meant to satisfy.
Architectural design therefore determines whether governance principles remain enforceable in practice.

Several architectural implications follow from the principles described in this paper.
Governance frameworks should ensure that authority boundaries remain explicit and that authority is verified at the point where actions occur rather than assumed from prior configuration.
Delegation chains should be represented in forms that allow their integrity to be verified during operation and reconstructed afterward if questions arise.
Policy conditions should be evaluated at the point of action so that authority is confirmed when it is exercised rather than assumed from earlier system state.

Systems should incorporate escalation and interruption mechanisms within automated decision pipelines, establishing defined conditions under which autonomous action is suspended and human review is required.
Logging and audit mechanisms should record the authority basis for actions, not only the actions themselves, so that governance authorities can determine whether delegated authority was exercised within its intended scope.

### Implementation considerations

Implementing governance requirements involves trade-offs that should be addressed explicitly.
Authority verification at the point of action may introduce latency; acceptable levels of delay depend on operational context and the consequences of acting on invalid authority.
Centralized policy evaluation promotes consistent interpretation of governance rules but may introduce dependencies affecting system resilience.
Rich representation of delegation relationships enables more precise governance but requires investment in identity and authorization infrastructure.

These trade-offs do not admit universal answers.
What matters is that they are recognized as governance decisions rather than technical optimizations.
Decisions that weaken authority verification, reduce observability, or relax enforcement constraints should therefore be treated as risk decisions requiring explicit authorization and documentation.

### Periodic Governance Re-Verification

Organizations should periodically verify that delegation structures, enforcement controls, and authority boundaries remain aligned with governance intent, ensuring that operational changes or system evolution do not undermine delegated authority.

### Alignment with emerging technical frameworks

Governance of delegated authority does not occur independently of technical standards and frameworks.
Developments in identity, authorization, policy expression, and auditability continue to evolve across technical communities.
Governance frameworks should remain aware of these developments while maintaining independence from any single implementation approach.

The objective of governance guidance is not to prescribe particular technologies but to define the requirements that operational systems must satisfy to preserve the integrity of delegated authority.
Where emerging technical frameworks provide mechanisms supporting these requirements — including delegation representation, runtime authority evaluation, policy communication across trust boundaries, and evidentiary logging — governance frameworks should recognize and engage with those developments.

Where such mechanisms remain incomplete or inconsistent, governance frameworks should identify the gap clearly so that technical standards development can address it.

## Conclusion

### The need for explicit governance of delegated authority in AI-mediated systems

As automated systems assume operational roles in decision and execution pipelines, governance of delegated authority becomes **more** demanding rather than **less**.
The structures through which authority is granted, constrained, and enforced must be made explicit in ways that human governance could previously leave implicit.
Accountability mechanisms must be designed into systems from the outset rather than reconstructed after the fact.
Oversight arrangements that ensure automated action remains an expression of human and institutional intent must be embedded in system architecture rather than assumed to follow from the presence of human actors elsewhere in the organization.

Delegation of authority, scope limitation, policy enforcement, and accountability are long-standing concerns in law, organizational governance, and information security.
What is new is the environment in which these principles must now operate: distributed systems functioning at machine speed, crossing organizational and technical boundaries, and acting on delegated authority several steps removed from the principal who originally granted it.
Governance models developed for human agents do not transfer directly into this environment.
Adapting them requires clarity about where those differences arise and deliberate design of mechanisms that address them.

### Future directions for standards and system design

This paper has identified several governance requirements that standards development will need to address: mechanisms for representing delegation scope and conditions in machine-interpretable form; communication of policy constraints across organizational boundaries in ways that receiving systems can evaluate; verification of authority at the point of action; maintenance of records that allow delegation chains and decision pathways to be reconstructed; and escalation and interruption mechanisms that preserve meaningful human oversight in automated decision pipelines.

Addressing these requirements will require continued collaboration between governance bodies and technical standards communities.
Clear articulation of governance expectations provides the foundation upon which interoperable technical mechanisms can be developed to ensure that delegated authority remains accountable, constrained, and consistent with the intent of the principals from whom it derives.

## Appendix: References, Standards Alignment, and Further Reading

The references and resources below identify the standards, literature, and regulatory instruments that informed the governance arguments in this paper.
They are organized to support further reading by working group members and to provide a foundation for standards development work in this area.
Sources are drawn from identity and authorization frameworks, scholarship on delegation and provenance in distributed systems, and relevant legal and regulatory instruments governing accountability and non-repudiation.
A section alignment table maps each paper section to relevant standards and implementation patterns, and a delegation representation comparison table evaluates current technical approaches against the paper's governance requirements.

### Standards and Frameworks

- RFC Editor. The OAuth 2.0 Authorization Framework. RFC 6749. 2012. https://www.rfc-editor.org/rfc/rfc6749
- RFC Editor. OAuth 2.0 Token Exchange. RFC 8693. 2020. https://www.rfc-editor.org/rfc/rfc8693
- RFC Editor. OAuth 2.0 Token Revocation. RFC 7009. 2013. https://www.rfc-editor.org/rfc/rfc7009
- RFC Editor. OAuth 2.0 Token Introspection. RFC 7662. 2015. https://www.rfc-editor.org/rfc/rfc7662
- RFC Editor. JSON Web Token (JWT). RFC 7519. 2015. https://www.rfc-editor.org/rfc/rfc7519
- RFC Editor. OAuth 2.0 Rich Authorization Requests. RFC 9396. 2022. https://www.rfc-editor.org/rfc/rfc9396
- RFC Editor. JSON Web Token (JWT) Profile for OAuth 2.0 Access Tokens. RFC 9068. 2021. https://www.rfc-editor.org/rfc/rfc9068
- RFC Editor. OAuth 2.0 Security Best Current Practice. RFC 9700. 2025. https://www.rfc-editor.org/rfc/rfc9700
- OpenID Foundation. OpenID Connect Core 1.0. 2014. https://openid.net/specs/openid-connect-core-1_0.html
- OpenID Foundation. OpenID for Verifiable Credential Issuance (OpenID4VCI). 2024. https://openid.net/specs/openid-4-verifiable-credential-issuance-1_0.html
- OpenID Foundation. OpenID for Verifiable Presentations (OpenID4VP). 2024. https://openid.net/specs/openid-4-verifiable-presentations-1_0.html
- OASIS. Assertions and Protocols for the OASIS Security Assertion Markup Language (SAML) V2.0. 2005. https://docs.oasis-open.org/security/saml/v2.0/saml-core-2.0-os.pdf
- OASIS. eXtensible Access Control Markup Language (XACML) Version 3.0. 2013. https://docs.oasis-open.org/xacml/3.0/xacml-3.0-core-spec-os-en.html
- Kantara Initiative. User-Managed Access (UMA) 2.0 Specifications. https://docs.kantarainitiative.org/uma/ 
- World Wide Web Consortium. Verifiable Credentials Data Model v2.0. W3C Recommendation. 2024. https://www.w3.org/TR/vc-data-model-2.0/
- World Wide Web Consortium. Decentralized Identifiers (DIDs) v1.0. W3C Recommendation. 2022. https://www.w3.org/TR/did-core/
- World Wide Web Consortium. PROV-DM: The PROV Data Model. W3C Recommendation. 2013.https://www.w3.org/TR/prov-dm/
- IETF SPIFFE. Secure Production Identity Framework for Everyone. https://spiffe.io/docs/latest/spiffe-about/overview/
- National Institute of Standards and Technology. Digital Identity Guidelines. NIST SP 800-63-3. 2017. https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-63-3.pdf
- National Institute of Standards and Technology. Guide to Attribute Based Access Control (ABAC) Definition and Considerations. NIST SP 800-162. 2014. https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-162.pdf
- National Institute of Standards and Technology. Security and Privacy Controls for Information Systems and Organizations. NIST SP 800-53 Rev. 5. 2020. https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-53r5.pdf
- National Institute of Standards and Technology.Guide to Computer Security Log Management. NIST SP 800-92. 2006. https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-92.pdf
- National Institute of Standards and Technology. Artificial Intelligence Risk Management Framework (AI RMF 1.0). NIST AI 100-1. 2023. https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf

### Academic and Industry Literature

- Saltzer, Jerome H. and Schroeder, Michael D. The Protection of Information in Computer Systems. Proceedings of the IEEE, 63(9). 1975. https://doi.org/10.1109/PROC.1975.9939
- Abadi, Martín et al.
- A Logic of Authentication. ACM Transactions on Computer Systems. 1993. https://dl.acm.org/doi/10.1145/138243.138249
- Google Research. Zanzibar: Google's Consistent, Global Authorization System. 2019. https://research.google/pubs/pub48190/
- OWASP. OWASP Top 10 for Large Language Model Applications. 2025. https://owasp.org/www-project-top-10-for-large-language-model-applications/
- MITRE. ATLAS: Adversarial Threat Landscape for Artificial-Intelligence Systems. https://atlas.mitre.org/
- Open Policy Agent. OPA Policy Engine Documentation. https://www.openpolicyagent.org/docs/latest/
- Cedar Policy Language. Cedar Policy Language Specification. https://docs.cedarpolicy.com/

### Legal and Regulatory

- European Union. Regulation (EU) 2024/1689 — Artificial Intelligence Act. 2024. https://eur-lex.europa.eu/eli/reg/2024/1689/oj
- European Union. Regulation (EU) 2016/679 — General Data Protection Regulation. 2016. https://eur-lex.europa.eu/eli/reg/2016/679/oj
- European Union. Regulation (EU) No 910/2014 — eIDAS Regulation.2014. https://eur-lex.europa.eu/eli/reg/2014/910/oj
- United States Congress. Electronic Signatures in Global and National Commerce Act (E-SIGN). Public Law 106-229. 2000. https://www.govinfo.gov/content/pkg/PLAW-106publ229/pdf/PLAW-106publ229.pdf
- American Law Institute. Restatement (Third) of Agency. 2006. https://www.ali.org/publications/show/agency/

### Section Alignment: Governance Paper to Standards and Frameworks

The table below maps each section of the paper to the most directly relevant standards, implementation patterns, and regulatory anchors.

- Section 1 — Introduction. NIST AI RMF for sociotechnical risk framing. EU AI Act risk-based obligations for AI systems.
- Section 2 — Authority in Sociotechnical Systems. Agency law concepts of principal, agent, attribution, and liability. eIDAS for digital trust services and evidentiary integrity.
- Section 3 — Delegation of Authority. OAuth token formats including JWT profile and token exchange. Token revocation and introspection. Caveated tokens including Macaroons for attenuation. Session policies for constrained delegation.
- Section 4 — Agents Operating Under Delegated Authority. OWASP LLM Top 10 covering prompt injection and excessive agency. MITRE ATLAS threat knowledge base. Agent tool authorization patterns using Cedar and OPA.
- Section 5 — Authority Boundaries in Distributed Systems. PDP/PEP pattern as formalized in XACML. Relationship-based authorization using Zanzibar-style systems for distributed permissions.
- Section 6 — Provenance, Traceability, and Accountability. EU AI Act record-keeping requirements for high-risk AI. NIST log management guidance SP 800-92. W3C PROV data model for provenance interchange. OpenTelemetry for distributed trace correlation.
- Section 7 — Enforcement of Authority. XACML PDP/PEP separation. OPA policy as code. Cedar authorization engine. OAuth security best current practice RFC 9700. Token exchange for delegation claims. Rich Authorization Requests RFC 9396.
- Section 8 — Risks in Delegated Authority Systems. OAuth token exchange act claim for delegation chain provenance. Caveated tokens including Macaroons and Biscuit for attenuation. Indirect prompt injection research. Cross-domain semantics gaps in authorization vocabularies.
- Section 9 — Human Oversight in Machine-Speed Environments. EU AI Act human oversight obligations for high-risk AI. NIST AI RMF governance across the AI lifecycle.
- Section 10 — Implications for Identity and Authorization Frameworks. OpenID Connect and SAML for identity assertions. W3C Verifiable Credentials and DIDs for portable credentials. OpenID4VCI and OpenID4VP for credential issuance and presentation. SPIFFE for workload identity across trust domains.
- Section 11 — Operationalizing Governance Principles. ISO/IEC 27001 and ISO/IEC 42001 management system approaches. NIST log planning guidance. OAuth security best current practice.
- Section 12 — Conclusion. GNAP evolution for next-generation delegated authorization. SD-JWT VC standardization. IETF SCITT transparency and receipt architecture for audit integrity.
 
### Delegation Representation Approaches

The following summarizes commonly deployed and emerging approaches for representing delegated authority, evaluated against the paper's governance requirements.

**OAuth 2.0 bearer tokens with introspection** — Machine evaluable via authorization server.
Partial provenance through server-side records.
Moderate constraint support via scopes and introspection claims.
Higher latency due to online dependency.
Very high maturity.
Widely deployed in existing systems; however, bearer tokens are possession-based credentials that carry an inherent risk of leakage and are not bound to the presenting party.
For governance-critical delegated authority contexts, sender-constrained alternatives such as DPoP-bound tokens are preferred.
Recommended only where revocation and real-time state checks are required and sender-constraining mechanisms are not yet available.

**OAuth 2.0 JWT access tokens (RFC 9068)** — Self-contained and machine evaluable.
Partial provenance via actor and audit ID claims.
Moderate constraint support via claims and scopes.
Lower latency through offline verification, though cryptographic validation cost may become a consideration at high call volumes.
High maturity.
Recommended for low-latency microservices where local validation is sufficient and cryptographic overhead is within acceptable bounds.

**OAuth 2.0 Token Exchange (RFC 8693) with actor chain** — Machine evaluable.
Strong provenance through explicit delegation trail.
Moderate constraint support depending on token content.
Medium latency due to authorization server exchange step.
High maturity.
Recommended for on-behalf-of flows and audit-critical delegation chains.

**OAuth Rich Authorization Requests (RFC 9396)** — Machine evaluable with structured authorization details.
Indirect provenance through logged request artifacts.
Strong constraint support for structured purpose-bound access.
Medium latency.
High maturity.
Recommended for payments, transactions, and fine-grained access requests.

**User-Managed Access (UMA 2.0)** — Machine evaluable through authorization server mediated policies.
Moderate provenance through ticket flows.
Strong constraint support through policy-driven grants.
Higher latency.
Medium maturity.
Recommended for asynchronous delegated authorization where resource owner policy is central.

**Verifiable Credentials (W3C VC 2.0) with DIDs** — Cryptographically verifiable.
Strong provenance for issuer and holder.
Variable constraint support depending on credential profile.
Low to medium verification cost.
Medium maturity.
Verifiable Credentials are designed for making claims about a subject — such as organizational role, certification, or identity attributes — rather than for expressing permissions directly.
They are appropriate for cross-organizational attestations of authority and regulated identity assertions requiring portability, where the credential conveys who a party is or what they have demonstrated, not what they are permitted to do.

**Caveated tokens (Macaroons)** — Machine evaluable through caveat checking.
Moderate provenance depending on implementation.
Strong contextual constraint support.
Low to medium latency.
Limited production deployment; while the concept is well-established and the design well-documented, Macaroons have not achieved broad industry adoption and should be evaluated carefully before use in governance-critical systems.
Recommended for delegation with attenuation across services and least-privilege token construction where implementation maturity has been verified.

**Biscuit attenuating tokens** — Machine evaluable with embedded logic and offline attenuation.
Moderate provenance through token blocks.
Strong fine-grained condition support.
Low to medium latency.
Emerging maturity.
Recommended for multi-tenant and microservice authorization where downstream attenuation is desirable.

**Relationship-based authorization (Zanzibar-style)** — Machine evaluable through graph query.
Strong provenance through centralized relation state and audit trails.
Strong expressive relation model support.
Medium latency due to query dependency.
High maturity proven at scale.
Recommended for large-scale multi-service permission systems requiring consistent evaluation.

### Delegation Chain Flow

The following describes the delegation chain governance model.
An originating principal delegates scope and conditions to an agent or delegate.
The agent redelegates a constrained scope to a downstream service.
That service passes further attenuated authority to additional downstream services.
Throughout this chain, organizational policy governs what is requested.
An authorization evaluation component (PDP) receives policy intent and evaluates whether proposed actions are authorized.
Enforcement points (PEP) at each service execution boundary receive the authorization decision and permit or block the action accordingly.

![flow diagram of a delegation chain](https://github.com/decentralized-identity/governance-of-delegated-authority-report/blob/main/assets/chain_flow_diagram.jpg?raw=true)

### Authorization Decision and Fail-Safe Flow

The following describes the authorization decision and fail-safe governance model.
A proposed action request enters the system.
Context is assembled including subject, actor, resource, action, and conditions.
The authorization evaluation component processes this context.
If the decision is allowed, the enforcement point permits the action to execute.
If the decision is denied, the action is blocked.
If the decision is indeterminate or the authorization service is unavailable, fail-safe handling applies.
Under fail-safe handling, state-changing actions default to deny.
Actions that warrant human judgment are routed to a human oversight queue.
All executed actions are logged with their authority basis, policy version, and outcome.
Where an action is denied, the invoker should be notified that the request was not authorized; notification should provide sufficient information to understand the basis for denial without disclosing policy internals or creating a basis for circumvention.

![lifecycle of a task]([./assets/lifecycle_of_a_task.jpg](https://github.com/decentralized-identity/governance-of-delegated-authority-report/blob/main/assets/lifecycle_of_a_task.jpg?raw=true))

## Open Research Questions and Standards Work to Watch

The following areas represent active development relevant to the governance requirements identified in this paper.

**Delegation semantics profiles** — OAuth Token Exchange supports actor chains but interoperable meaning for actor attributes and constraint claims remains under-specified.
In JWT-based delegation, the subject (sub claim) identifies the principal on whose behalf the token is issued, while the actor (act claim, RFC 8693) identifies the delegate actively presenting and exercising the token; in delegated authority contexts these are distinct, and conflating them obscures accountability.
Profiles and conformance tests that clarify this distinction and establish interoperable meaning for actor attributes and constraint claims represent a practical standards gap.

**Authorization vocabulary standardization** — Rich Authorization Requests enable structured authorization details but cross-domain schemas require shared profiles to avoid valid-but-different-meaning failures across organizations.
Credential ecosystem convergence — W3C VC 2.0, OpenID4VCI and OpenID4VP, and IETF SD-JWT VC efforts are converging on interoperable credential structures.
The remaining gap is authorization semantics and constraint evaluation across organizational boundaries.

**AI-specific threat modeling** — OWASP LLM Top 10 and MITRE ATLAS provide evolving taxonomies for delegated tool use and prompt injection.
The standards question is how to encode tool authority and execution constraints in interoperable forms.
Transparency and tamper-evident records — IETF SCITT is developing architectures and receipt profiles for transparent verifiable audit trails potentially applicable to delegation provenance and evidence chains.

**Next-generation authorization protocols** — GNAP continues to evolve delegated authorization concepts beyond OAuth's historical constraints.
Monitor maturity and ecosystem adoption before standardizing for governance-critical systems.

**Operational security guidance evolution** — The OAuth security best current practice RFC 9700 and ongoing update drafts indicate that threat models and recommended defaults evolve.
Governance programs should include a standards-monitoring control.

## Patent Policy

The Decentralized Identity Foundation has adopted the W3C Patent Policy (2004), as detailed below:

- **Licensing Commitment.** Each contributor agrees to make available any of its
  Essential Claims, as defined in the W3C Patent Policy (available at
  http://www.w3.org/Consortium/Patent-Policy-20040205), under the W3C RF licensing
  requirements Section 5 (http://www.w3.org/Consortium/Patent-Policy-20040205), as
  if the contribution was contained in or associated with a W3C Recommendation.

- **For Exclusion.** Prior to committing any code, bug reports, pull requests, or
  other forms of contribution, a contributor may exclude Essential Claims from its
  licensing commitments under this agreement by providing written notice of that
  intent to DIF's Executive Director (and must received confirmation of receipt
  for the exclusion to have effect).
The Exclusion Notice for issued patents and
  published applications must include the patent number(s) or title and
  application number(s), as the case may be, for each of the issued patent(s) or
  pending patent application(s) that the contributor wishes to exclude from the
  licensing commitment set forth in Section 1 of this patent policy.
If an issued
  patent or pending patent application that may contain Essential Claims is not
  set forth in the Exclusion Notice, those Essential Claims shall continue to be
  subject to the licensing commitments under this agreement.
The Exclusion Notice
  for unpublished patent applications must provide either: (i) the text of the
  filed application; or (ii) identification of the specific part(s) of the
  contribution whose implementation makes the excluded claim an Essential Claim.
  If (ii) is chosen, the effect of the exclusion will be limited to the identified
  part(s) of the contribution.
DIF's Executive Director will publish Exclusion
  Notices.
