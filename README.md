EPIC Ops Redo — Wireframe Guide

What this is
- A high-fidelity wireframe for the NSW EPA EPIC system. It demonstrates layout, and workflow changes
- Content, data, and logic are mocked to explain intent. Many buttons open in-product notes instead of performing real transactions.

Key shifts from current EPIC
- Notifications are removed; the system starts with cases. Related cases can be linked instead of duplicating notifications.
- Case lifecycle is simplified to Open → Closed (no intermediate stages).
- Regulatory triage replaces legacy classifications. 
- Case Summary becomes the landing page for contextual info. 
- Notice compliance is stored against the notice itself, not in a separate section.
- Proposed email-to-case capture: officers forward mail to a designated mailbox, the case number in the subject is parsed (e.g., “EPA-1234”), and if the officer has write access the email file is attached and logged.
- Case title: Static case number + editable case name. Pencil toggles editing; icon flips to a save indicator while editing.

Global interactions and notes
- Notes panel: Most icons/buttons open a note card explaining the intended behaviour. Notes live in `/notes` and load via `loadNote()`.
- Case notes: Shown inline or alongside tabs (toggleable). Adding a note appends to the log; mock data is seeded in `caseNotes`.

Screens

My Work (default landing)
- Two table views (Open/Closed) toggled in-place; shows case name, creator, triage score, due date, and reported date.
- Links open the example case or secondary record.
- Task list shows notices, actions, reminders; “Next page” arrows open explanatory notes.

Dashboard
- Placeholder card describing the future team dashboard (mirrors My Work at team level, highlights who holds actions/cases and for how long).

Secondary Record (SR-123 example)
- Actions dropdown allows returning to case and shows audit/terminate/refresh via notes.
- Body shows notice type summary, responsible officer with reallocate note, and “Edit in Word” note describing editing.
- POI selector with “switch chosen POI” note for serving notices.
- Notice compliance now recorded against notices instead of its own section and file upload note.

Case tabs

Summary
- Case title block: fixed case number + editable case name (pencil toggles to save icon while editing; read-only look matches static text).
- Meta strip: discovered/reported/created dates and source.
- Responsible officer/access line with reallocate/access-change notes.
- Regulatory triage snapshot (score label updates from triage inputs elsewhere).
- Open tasks table (links to secondary record or notes) and Linked Cases table.
- Note icon opens the “Case Summary” explainer.

Details
- Simplified incident form. Starts read-only; Edit toggles fields to writable; Save/Discard return to read-only.
- Note explains which legacy fields were removed, which are inferred, and why.

Location
- Shows address and embedded map. “Edit Location” opens a note describing address/map edit flows and saving the pin/address back to the case.

POIs / Vehicles
- Combined POIs and Vehicle tabs. 
- POIs table with categories, licences, addresses; row menu opens a placeholder edit note. “Add POI” opens note describing capture and auto case note.
- Vehicles table includes owner details and a sample vehicle. “Create DRIVES Request” opens a note describing pre-populating DRIVES with the vehicle/registration/VIN/context.

Documents
- Combine notices, reports and regulatory actions tabs. 
- Three sections: Notices, Reports/Other Documents, Regulatory Actions. Each has a green “New …” button that drops down template options.
- Selecting any template navigates to the secondary record mock (SR-123).
- Notices table shows a sample s.191 notice linked to the suspect.

Attachments (Files)
- Upload button opens note covering file uploads. 
- Attachmets should allow many files to the one single attachment secondary record. 
- A shortcut to the new attachment screen should be dragging a file in the case note, which pre-populates the new attachment screen which comes up, with the dragged file. 

Closure
- Final case note is rendered (last entry in `caseNotes`). Open documents listed with reminder they’ll be terminated on closure.
- Triage controls repeat here; primary score shows; secondary risk fields appear when score is high. Note explains triage intent. “Finalise Closure” opens closure steps note (unit head email, approve/reject links).

Notes referenced (high level)
- caseSummaryNote: purpose of the Summary landing page.
- incidentDetailsNote: why Details is trimmed and where fields moved.
- explainTriageNote/triageExplanation: how the new triage works and drives due dates.
- newPOINote: adding POIs/vehicles logs a case note.
- createDrivesRequest: DRIVES request starts pre-filled from the vehicle row.
- addAction: actions behave like a case to-do with reminders.
- editLocationButton: address vs map editing flow.
- uploadFile: upload flow and automatic case note; supports multi-file.
- reallocate: reassigning responsible officer logs a note.
- openInWord: download/edit documents in Word.
- closeCaseButton: closure confirmation, unit head email, approve/reject links.
- switchChosenPOI: pick which POI a notice is served to.
