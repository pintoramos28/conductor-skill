# Lessons Learned

## Feedback Log
- User request: add a lessons learned document to capture feedback and improve the skill.
- User feedback: the `product.md` file only reflected the initial prompt and did not include answers from the Q&A before approval.
- User feedback: the initial tech stack recommendations did not include a testing stack.
- User feedback: for greenfield projects and brownfield feature work, tech stack recommendations should include more detail on pros/cons for each option.
- User feedback: spec and plan documents do not include traceability between requirements, tasks, acceptance criteria, tests, and user stories.
- User feedback: questions used to draft documents should be embedded in the documents themselves so users can answer/edit directly in one place.
- User feedback: after each feedback iteration, the skill should analyze responses using references/research and then provide consolidated feedback and follow-up questions across all sections at once (not one-by-one).
- User feedback: recommendations can continue if beneficial, but must stop once the user says they’re happy and explicitly doesn’t want more; then proceed to the next step.
- User feedback: tech stack should include version recommendations for clarity; versions should be updated if compatibility issues are discovered later.
- User feedback: for large greenfield builds, a single track can be too broad; the scope should split into multiple tracks (e.g., data prep + table, core plotting, advanced plotting/interactivity) or be structured into smaller, assessable phases/tasks.
- User feedback: skill lacks a clear mechanism for updating requirements/plan mid‑stream as new constraints emerge (e.g., limiting data table rows).
- User feedback: prefer a hybrid approach with a project-level spec plus track-level deltas; completed track specs should be consolidated into the project spec.
- User feedback: for design-phase feedback, edits should be applied directly in documents and the agent should review the full document before updating with edits/questions/clarifications.

## Observations From This Session
- The product guide draft was generated and presented for approval, but it was not written to `product.md` yet. This created confusion when the user expected the file to already include the answers. The flow should make the “draft vs. saved” state explicit and visible in the file system, or write a clearly labeled draft file automatically.
- The user asked to “modify with external editor,” which implies they expect a real file containing the latest draft. The workflow could improve by writing a draft to `product.md` (or `product.draft.md`) immediately and then reconciling approval changes.
- The user’s request to read the Essential Graphing document is a strong signal that the skill should explicitly acknowledge and summarize how external docs are being used to shape the product guide.

## Suggested Improvements to the Context-Driven Dev Skill
1. **Draft Persistence:** When a draft is generated, write it to disk as `context/product.draft.md` (or overwrite `product.md` with a clearly marked “DRAFT” header) so external editors see the latest draft immediately.  
   - **Proposed update:** Extend draft persistence to all core docs (`product`, `tech-stack`, `workflow`, `spec`, `plan`) using a consistent `*.draft.md` convention and a visible DRAFT banner.  
   - **Notes for feedback:** 
2. **State Clarity:** After presenting a draft, explicitly state whether `product.md` has been updated or not. Provide a one-line status like: “Draft saved to …” or “Draft not yet saved.”  
   - **Proposed update:** N/A (rejected per feedback).  
   - **Notes for feedback:** I don't want this included
3. **External Editor Workflow:** If the user says “modify with external editor,” automatically save the current draft to the target file (or draft file) and respond with the full path.  
   - **Proposed update:** Make this the default behavior and include a short “editing guide” block inside the doc (where to respond, how to mark edits, how to signal done).  
   - **Notes for feedback:** Use this as the default option
4. **Doc Usage Transparency:** When the user supplies reference docs, add a short “Sources Used” section or note in the draft to show how those docs influenced the output.  
   - **Proposed update:** N/A  
   - **Notes for feedback:** This is good.
5. **Question Loop UX:** When a user changes a previous answer, the skill should confirm that prior selections were discarded and restate the current captured selections before moving on.  
   - **Proposed update:** N/A  
   - **Notes for feedback:** This is good.
6. **Testing Stack in Tech Recommendations:** Include a default testing toolchain recommendation in the initial tech stack draft, and call out whether unit/integration/e2e tools are chosen or still open.  
   - **Proposed update:** N/A  
   - **Notes for feedback:** This is good.
7. **Pros/Cons in Tech Stack Guidance:** Provide more detailed, context-aware pros/cons for each tech option, especially for greenfield setups and brownfield feature additions.  
   - **Proposed update:** Always list recommended versions in tech stack options and update them when incompatibilities are discovered; apply alongside the base recommendation.  
   - **Notes for feedback:** The proposed update and the original item seem additive. DO both.
8. **Traceability by Default:** Generate or prompt for a traceability matrix linking requirements ↔ plan tasks ↔ tests ↔ acceptance criteria ↔ user stories as a standard artifact.  
   - **Proposed update:** Add a minimal default matrix in the plan template: `Req ID → Task ID → AC → Test ID`.  
   - **Notes for feedback:** This is good.
9. **Document-Embedded, Document-First Feedback:** Replace sequential Q&A with document-embedded question sections and direct edits so users can respond in one place and review holistically, and require a full-document review before applying updates or follow-up questions.  
   - **Proposed update:** Embed a “Q&A snapshot” section in each draft and carry it into the approved document.  
   - **Notes for feedback:** This is good.
10. **Batch Feedback Cycles:** After ingesting responses, provide consolidated analysis and a single batch of follow-up questions across all sections, informed by references and research.  
    - **Proposed update:** Ensure batch feedback explicitly incorporates the Q&A snapshot/context from #9.  
    - **Notes for feedback:** This is good and should keep #9 in mind during implementation.
11. **User‑Controlled End Condition:** Offer recommendations when useful, but if the user says they’re happy and wants to stop, end the loop and move to the next step.  
    - **Proposed update:** N/A (applies within #10 batch feedback flow).  
    - **Notes for feedback:** This is a note for the batch feedback cycles
12. **Versioned Tech Stack:** Provide recommended library versions upfront and update them when incompatibilities or constraints surface.  
    - **Proposed update:** N/A  
    - **Notes for feedback:** This is good.
13. **Track Sizing & Scoping Guidance:** For large greenfield projects, provide guidance and examples to split scope into multiple tracks or structure a larger track into smaller, assessable phases/tasks aligned to data prep, core plotting, and advanced interactions/analytics.  
    - **Proposed update:** N/A  
    - **Notes for feedback:** This is good.
14. **Change Management:** Add a lightweight process for updating requirements and plans during implementation (e.g., change log + plan adjustment steps).  
   - **Proposed update:** N/A (rejected per feedback).  
   - **Notes for feedback:** Don't do this.
16. **Hybrid Spec Model:** Maintain a project-level spec for stable requirements and track-level deltas; consolidate completed track specs back into the project spec.  
   - **Proposed update:** N/A (covered by #17).  
   - **Notes for feedback:** This is good. this is covered in #17
17. **Requirements Index:** Maintain a small project-level index mapping requirements to track specs and plan tasks for cross-track visibility.  
    - **Proposed update:** N/A  
    - **Notes for feedback:** This is good
18. **Decision Log (ADRs):** Add a lightweight decision log to capture mid-stream changes and rationale (e.g., table row limits), aiding future track planning.  
   - **Proposed update:** Require ADR IDs to be referenced in plan tasks for any mid-stream change.  
   - **Notes for feedback:** This is good.
