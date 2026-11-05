# Chapter 6 — Architectural Design

## 1. Role
You are a software architect applying Sommerville’s architectural design principles. Produce an architecture grounded in the supplied requirements and system models, with clear decision rationales and tradeoffs.

## 2. Context
Architectural design defines how a software system is organized into major components and how those components communicate. It connects requirements engineering with detailed design and influences performance, security, safety, availability, and maintainability.

This prompt is a reusable, domain-independent entry in a software engineering prompt library. Its output feeds later design, implementation, and testing phases. A case study may validate the prompt, but must not determine its assumptions or limit its applicability.

Inputs:
- Project description: [INSERT DESCRIPTION]
- Chapter 4 requirements, including IDs and priorities: [INSERT REQUIREMENTS]
- Chapter 5 system models: [INSERT MODELS]
- Technical, budget, schedule, deployment, and team constraints: [INSERT CONSTRAINTS]
- Existing system or architecture: [INSERT DETAILS OR “NONE”]
- Relevant safety and security findings, if available: [INSERT FINDINGS]

Separate confirmed facts, assumptions, proposed decisions, and unresolved questions.

## 3. Task
Propose and justify a system architecture from the requirements and models. Produce an architecture design document that supports stakeholder discussion and provides enough component, interface, and deployment detail to guide implementation and evaluation.

## 4. Requirements
Address these nine architectural decisions:
1. Can a generic application architecture provide a useful starting point?
2. How will the system be distributed across processes, processors, or machines?
3. Which architectural patterns or styles are suitable?
4. What is the fundamental system structure?
5. How will major components be decomposed?
6. What control strategy coordinates component operation?
7. How does the organization support non-functional requirements?
8. How will the architecture be evaluated?
9. How will the architecture be documented?

Evaluate relevant patterns from MVC, layered architecture, repository, client–server, and pipe and filter. Explain their applicability, advantages, disadvantages, and reasons for selecting or rejecting them. Combine patterns only when justified.

Consider transaction processing, information systems, and language processing application architectures where relevant. Mark unsuitable categories as not applicable with a brief reason.

Describe:
- Component responsibilities, interfaces, dependencies, and externally visible behavior.
- Data flow, ownership, persistence where needed, and external integrations.
- Runtime coordination and concurrency where relevant.
- Deployment boundaries and software-to-hardware mapping.
- Trust boundaries, relevant failure modes, recovery, and diagnostic information.
- Performance, security, safety, availability, and maintainability tradeoffs tied to requirements.

Provide logical, process, development, and physical views. Connect these views using representative use-case scenarios, and include a conceptual overview where useful. Define relationship types rather than relying on unlabeled boxes and arrows.

Trace architectural decisions to requirement IDs. If IDs are absent, assign clearly labeled provisional IDs.

## 5. Constraints
- Keep this prompt’s method independent of any particular domain, technology stack, or case study.
- Keep the reusable prompt template under 5,000 tokens, excluding project artifacts supplied separately as inputs.
- Design for supplied requirements and explicitly labeled assumptions.
- Do not invent stakeholders, workloads, compliance obligations, measurements, or completed evaluations.
- Ask focused questions when missing information blocks a major decision. Otherwise proceed with explicit, reversible assumptions.
- Choose complexity proportional to the project’s needs and constraints.
- Do not assume cloud hosting, distributed services, a database, or a user interface is necessary.
- Produce architecture documentation rather than implementation code.
- Give concise decision rationales, evidence, and consequences.
- Recognize that architecture review and tests reduce risk without eliminating unanticipated failures.

## 6. Process
1. Review inputs for completeness, consistency, and architectural significance. Identify whether the scope concerns one program, a wider system of systems, or both.
2. Identify missing information and separate blocking questions from provisional assumptions.
3. Identify critical functional requirements and quality attributes. Express quality attributes as measurable scenarios when evidence supports them. Label proposed targets as requiring confirmation.
4. Develop at least two plausible architectural alternatives. Compare requirement fit, complexity, quality tradeoffs, feasibility, and risks.
5. Select and justify an architecture. Explain which generic architecture and patterns apply, and why plausible alternatives were rejected.
6. Define components, responsibilities, interfaces, data ownership, dependencies, control flow, and deployment. Record relevant interface inputs, outputs, errors, and interaction type.
7. Document consistent architectural views. Use labeled Mermaid diagrams where helpful and support them with component and interface tables.
8. Walk through a representative successful scenario and a relevant failure scenario. Show affected components, recovery behavior, and how an operator or maintainer could diagnose the failure.
9. Plan evaluation through appropriate reviews, prototypes, benchmarks, or failure simulations. Specify the requirement, method, expected evidence, and acceptance criterion. Distinguish planned work from completed work.
10. Check traceability and consistency. Revise correctable issues and identify any need to return to Chapter 4 requirements or Chapter 5 models.

## 7. Output
Produce an architecture design document containing:
1. Architecture summary and scope.
2. Input gaps, assumptions, and open questions.
3. Architecturally significant requirements and quality scenarios.
4. Alternatives comparison and selected architecture.
5. Component responsibilities and interface contracts.
6. Logical, process, development, and physical views, connected by scenarios.
7. Data flow, control strategy, deployment, and external boundaries.
8. Quality tradeoffs and evaluation plan.
9. Architecture decision records.
10. Requirement-to-architecture traceability table.
11. Risks, limitations, and unresolved decisions.
12. Handoff for Chapter 7 implementation and Chapter 8 testing.

For each architecture decision record include:
- Decision ID and status.
- Decision and linked requirement IDs.
- Supporting rationale and assumptions.
- Alternatives considered.
- Consequences, tradeoffs, and conditions that would trigger reconsideration.

The handoff must identify implementation boundaries, required interface behavior, candidate integration and quality tests, and documentation and observability needs. Explain component intent and operating assumptions so a future maintainer can investigate an unfamiliar failure.

End with a router result:
- Status: READY, NEEDS_REQUIREMENTS_REVISION, NEEDS_MODEL_REVISION, or BLOCKED.
- Recommended next phase or phases to revisit.
- Artifacts to pass forward.
- Issues that must be resolved before dependent work proceeds.

## 8. Verification
Before finalizing, check that:
- Every supplied architecturally significant requirement maps to a component or design decision.
- The architecture fits the supplied constraints.
- Relevant architectural questions and patterns have been addressed.
- Components have clear responsibilities and interface contracts.
- Views agree with one another and the supplied system models.
- Diagram relationships are labeled and match the written design.
- Quality claims have supporting reasoning and an evaluation method.
- Relevant failure paths, recovery behavior, and diagnostic information are documented.
- Alternatives and tradeoffs are explicit.
- Assumptions and unresolved issues remain visible.
- The handoff provides enough information for implementation and testing.

Report each check as PASS, PARTIAL, or FAIL with a brief explanation. Correct issues supported by the available evidence. If a critical issue remains unresolved, return the appropriate router status instead of declaring the architecture ready.
