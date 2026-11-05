# Build ProSite — Construction & Commercial Management SaaS

**Developed by:** M and S Construction Tech  
**Product:** ProSite  
**Commercial Module:** QuoteFlow  
**Target Market:** Indian construction SMEs, contractors, developers, architects, site engineers and project managers.

---

# 1. PRODUCT VISION AND OVERVIEW

Act as a senior full-stack developer, SaaS product architect, database architect and UI/UX designer.

Build a complete, responsive, mobile-first construction and commercial management web application named **ProSite**, developed by **M and S Construction Tech**.

ProSite is designed to digitise and streamline construction project management and commercial operations for small and medium-sized construction businesses in India.

It combines construction site management with an integrated commercial management module called **QuoteFlow**.

## The problem

Many Indian construction SMEs still depend on manual processes such as:

- WhatsApp groups for project communication.
- Paper-based daily site diaries.
- Excel spreadsheets for expenses and budgets.
- Manual labour attendance registers.
- Separate records for materials and procurement.
- Word documents and spreadsheets for quotations and invoices.
- Disconnected tools for client communication and progress reporting.

These practices create several problems:

- Poor accountability.
- Cost overruns.
- Delayed project completion.
- Inaccurate material and labour records.
- Difficulty tracking project profitability.
- Poor visibility into site progress.
- Delayed invoicing and payment collection.
- Difficulty maintaining organised project documentation.

## The proposed solution

ProSite will provide one connected platform to manage the complete construction business workflow.

It should cover:

- Construction projects and milestones.
- Clients and project teams.
- Estimates and quotations.
- Daily site progress logs.
- Labour attendance and payroll-related tracking.
- Material inventory and procurement.
- Tasks and deadlines.
- Project budgets and expenses.
- Invoices and payment records.
- Documents, drawings and photographs.
- Client-facing progress reports.
- Business analytics and project performance.

The product must be affordable, practical, easy to learn and suitable for businesses that do not have dedicated IT teams.

## Product philosophy

Prioritise:

1. Practical functionality over unnecessary complexity.
2. Accurate financial calculations.
3. Connected records rather than disconnected modules.
4. Mobile usability for people working on construction sites.
5. Clear accountability and traceability.
6. Affordable implementation for Indian SMEs.
7. A scalable architecture that can support multiple companies in the future.

The owner has basic coding knowledge and a zero-rupee starting budget. Prefer free and open-source technologies wherever practical.

---

# 2. PRODUCT OBJECTIVE AND CORE WORKFLOW

Create one connected system for managing the following:

- Construction projects.
- Clients and project teams.
- Estimates and quotations.
- Daily site logs and progress.
- Worker attendance and labour costs.
- Material inventory and usage.
- Tasks and deadlines.
- Budgets and expenses.
- Invoices and payment records.
- Reports and project documentation.

The key business workflow is:

**Client → Estimate → Quotation → Accepted Quotation → Project → Site Operations → Actual Expenses → Invoice and Payment Records → Project Reports → Handover**

Every related record must be connected through stable project IDs, customer IDs and other appropriate relationships.

Do not create disconnected copies of the same records.

For example:

- A quotation must belong to a client.
- An accepted quotation can create or link to a project.
- A project must contain its site operations and financial records.
- Material usage should be traceable to the relevant project.
- Expenses should be linked to the relevant project and category.
- Invoices should be linked to clients and, where applicable, projects.
- Payments should be recorded separately and linked to invoices.
- Reports should calculate their information from actual stored records.

---

# 3. TECHNOLOGY AND ARCHITECTURE

Use the following technology stack for the initial MVP:

| Layer | Technology |
|---|---|
| Frontend | React |
| Language | TypeScript |
| Build tool | Vite |
| Styling | Tailwind CSS |
| Navigation | React Router |
| Icons | Lucide React |
| Charts | Recharts or a suitable maintained alternative |
| PDF | Browser printing or a maintained PDF library |
| Initial database | localStorage |
| Larger local files | IndexedDB |
| Future database | PostgreSQL |
| Future authentication | Supabase Auth |
| Future storage | Supabase Storage or compatible private storage |
| Future hosting | Suitable free-tier hosting |

## Architecture requirements

- Use a modular frontend architecture.
- Separate UI components, business logic, validation and data services.
- Create a repository/data-service layer so browser storage can eventually be replaced with PostgreSQL without rewriting the entire UI.
- Use reusable components and consistent design tokens.
- Implement a versioned local data schema.
- Use stable unique IDs.
- Use timestamps and preserve relationships.
- Handle missing, malformed or outdated data safely.
- Use decimal-safe monetary calculations.
- Avoid hardcoding dashboard metrics after records begin being created.

## Initial prototype limitations

The first version may use local browser storage.

However:

- Do not pretend that local records are securely shared between devices.
- Do not implement fake authentication.
- Do not claim that browser storage is a cloud database.
- Clearly explain that clearing browser data may cause data loss.
- Provide JSON export and validated import.
- Provide a clear future migration path to Supabase and PostgreSQL.

## Future production architecture

Plan for:

- Supabase authentication.
- PostgreSQL database.
- Row-level security.
- Company-level and project-level access control.
- Private cloud file storage.
- Secure backend validation.
- Database constraints.
- Backups and recovery.
- Multi-device synchronisation.

Do not require paid APIs for the initial version.

---

# 4. DESIGN SYSTEM AND USER EXPERIENCE

Create a premium, professional construction SaaS interface inspired by the clarity and usability of Monday.com and Asana, without copying their branding.

## Brand colours

| Element | Colour |
|---|---|
| Primary blue | #2196F3 |
| Success green | #4CAF50 |
| Warning orange | #FF9800 |
| Background | #F5F7FA |
| Main text | #333333 |
| Borders | #E0E0E0 |

Use Poppins-style headings and Inter-style body text.

## Interface requirements

Provide:

- Collapsible desktop sidebar.
- Mobile-first navigation.
- Responsive tables and cards.
- Search, sorting and filtering.
- Status badges.
- Accessible forms.
- Dark mode.
- Loading states.
- Empty states.
- Error states.
- Clear confirmation dialogs for destructive actions.
- Consistent spacing, typography and icons.
- Useful tooltips and form validation.
- Responsive layouts for desktop, tablet and mobile.

The interface must look and feel like a professional SaaS product, not a static dashboard template.

Every visible navigation item and button must perform its advertised action.

---

# 5. MAIN NAVIGATION AND MODULES

Create the following main navigation:

1. Dashboard
2. Projects
3. Clients

**QuoteFlow — Commercial Management**
- Estimates
- Quotations
- Invoices
- Change Orders
- Payment Records

**Site Operations**
- Daily Logs
- Tasks
- Attendance
- Materials

**Financial Management**
- Budgets
- Expenses
- Cost Variance

**Workspace**
- Documents & Photos
- Reports
- Team & Permissions
- Settings
- Business Profile

Each section must have its own functional interface and connect to the shared data model.

---

# 6. DASHBOARD

Create a central business dashboard.

Display:

## Project overview
- Active projects.
- Completed projects.
- Overdue projects.
- Overall project progress.
- Upcoming milestones.
- Projects requiring attention.

## Financial overview
- Total approved project budgets.
- Estimated contract value.
- Actual recorded project costs.
- Budget remaining.
- Over-budget projects.
- Total invoices issued.
- Outstanding invoice balances.
- Payments received.

## Site operations
- Recent site logs.
- Pending tasks.
- Low-stock materials.
- Attendance summary.
- Upcoming deadlines.

## Additional functionality
- Project search.
- Date filters.
- Status filters.
- Quick actions.
- Recent activity.
- Recent documents.

All metrics must be calculated from actual records.

Clearly distinguish:

- Estimated contract value.
- Approved project budget.
- Recorded expenses.
- Invoices issued.
- Payments received.
- Outstanding balances.

Never treat these financial values as interchangeable.

---

# 7. PROJECT MANAGEMENT

Create a complete project management module.

## Project fields

- Project name.
- Unique project ID.
- Client.
- Site address.
- Start date.
- Target completion date.
- Contract value.
- Approved baseline budget.
- Current status.
- Construction stage.
- Progress percentage.
- Project manager.
- Description.
- Notes.

## Functionality

Support:

- Creating projects.
- Editing projects.
- Viewing project details.
- Archiving projects.
- Searching projects.
- Filtering by status, client and manager.
- Viewing linked quotations.
- Viewing project expenses.
- Viewing site logs.
- Viewing tasks.
- Viewing materials.
- Viewing documents.
- Viewing financial performance.

Each project should have a dedicated project workspace containing all related information.

---

# 8. CLIENT MANAGEMENT

Create a client database.

## Client fields

- Individual or business name.
- Client type.
- Contact person.
- Phone.
- Email.
- Address.
- Optional GSTIN.
- Notes.
- Linked projects.
- Linked estimates.
- Linked quotations.
- Linked invoices.

Support creating, editing, searching, viewing and archiving clients.

Preserve relationships when client records are edited.

---

# 9. QUOTEFLOW — COMMERCIAL MANAGEMENT

QuoteFlow is an integrated commercial management module within ProSite.

It should manage the commercial lifecycle from initial estimation to quotation, approval, change orders, invoicing and payment records.

## 9.1 Estimates

Allow users to create detailed project estimates.

Support:

- Estimate number.
- Client.
- Optional project.
- Estimate date.
- Description.
- Construction work items.
- Materials.
- Labour.
- Machinery.
- Transport.
- Other costs.
- Quantities.
- Units.
- Rates.
- Line totals.
- Discounts.
- Optional tax.
- Notes.
- Terms and conditions.

Automatically calculate line totals and document totals.

## 9.2 Quotations

Allow users to convert estimates into quotations.

Features:

- Unique quotation numbers.
- Professional A4 layout.
- Company branding.
- Client details.
- Itemised work descriptions.
- Quantities and units.
- Rates and totals.
- Configurable discounts.
- Configurable tax.
- Payment terms.
- Validity dates.
- Terms and conditions.
- Save, edit and duplicate.
- Preview and print.
- PDF output.

Quotation statuses:

- Draft.
- Sent.
- Accepted.
- Rejected.
- Expired.

Allow an accepted quotation to be converted into a project or linked to an existing project.

**Important:** Preserve the accepted quotation as the original approved commercial baseline. Later changes must not silently rewrite its original amount.

## 9.3 Change Orders

Implement change-order management.

Record:

- Change-order number.
- Project.
- Client.
- Requested change.
- Reason.
- Description.
- Cost impact.
- Time impact.
- Approval status.
- Approval date.
- Supporting documents.

Only approved change orders should affect applicable project budget or contract calculations.

Keep an audit trail of changes.

## 9.4 Invoices

Support:

- Unique invoice number.
- Client.
- Project.
- Invoice date.
- Due date.
- Line items.
- Configurable tax.
- Discounts.
- Total amount.
- Amount paid.
- Outstanding balance.
- Payment status.
- Notes and terms.

Invoice statuses may include:

- Draft.
- Issued.
- Partially paid.
- Paid.
- Overdue.
- Cancelled.

An invoice must not become paid merely because it has been printed.

## 9.5 Payment Records

A payment must be a separate record linked to the relevant invoice.

Record:

- Payment ID.
- Invoice.
- Client.
- Project.
- Payment date.
- Amount.
- Payment method.
- Transaction reference.
- Notes.

Support multiple payments against one invoice.

Calculate outstanding balances using payment records.

## 9.6 Indian tax configuration

Make tax configuration explicit and optional.

Support configurable:

- CGST.
- SGST.
- IGST.
- Other applicable tax settings where required.

Do not automatically claim legal or tax compliance.

Allow the business to configure the tax treatment applicable to its transactions.

---

# 10. PROJECT BUDGETS AND EXPENSES

Each project must have a financial management workspace.

## Budget management

Support:

- Approved budget.
- Budget categories.
- Estimated costs.
- Actual expenses.
- Linked labour costs.
- Linked material costs.
- Approved change-order adjustments.
- Budget remaining.
- Budget variance.

## Expense categories

- Materials.
- Labour.
- Machinery.
- Transport.
- Subcontractors.
- Permits.
- Miscellaneous.

## Expense records

Record:

- Expense ID.
- Project.
- Date.
- Category.
- Description.
- Amount.
- Supplier.
- Payment method.
- Optional material reference.
- Optional invoice reference.
- Optional supporting document.

## Financial formulas

Actual expenses = Sum of recorded project expenses.

Applicable approved budget = Original approved budget + Approved budget adjustments.

Budget remaining = Applicable approved budget − Actual expenses.

Budget variance = Actual expenses − Applicable approved budget.

Positive budget variance means the project is over budget.

Negative budget variance means the project is under budget.

Avoid double-counting material and labour costs if they are already represented by linked expense records.

Make the source of every financial figure traceable.

---

# 11. DAILY LOGS AND SITE PROGRESS

Create a daily site diary.

Support:

- Daily site reports.
- Date.
- Project.
- Work completed.
- Issues and delays.
- Site observations.
- Weather.
- Manpower notes.
- Construction stage.
- Progress updates.
- Photos and attachments.
- Recorded by.
- Date-based filtering.

Provide daily, weekly and monthly views.

## Construction stages

Provide editable templates for:

- Excavation.
- Foundation.
- Structural work.
- Masonry.
- Electrical and plumbing.
- Finishing.
- Handover.

Allow managers to define milestones and completion percentages.

Do not assume that the average completion of unrelated tasks automatically represents accurate construction progress.

Make the progress calculation method explicit and configurable.

---

# 12. TASK MANAGEMENT

Create a project-based task management system.

Task fields:

- Task ID.
- Title.
- Description.
- Project.
- Assigned demo user.
- Priority.
- Due date.
- Status.
- Completion date.
- Notes.

Task statuses:

- To Do.
- In Progress.
- Blocked.
- Completed.

Support:

- Creating tasks.
- Editing tasks.
- Assigning tasks.
- Changing status.
- Filtering by project, priority and assignee.
- Overdue task indicators.
- Upcoming deadlines.

---

# 13. LABOUR ATTENDANCE

Create a labour and attendance management module.

Record:

- Worker name or ID.
- Role.
- Project.
- Date.
- Check-in.
- Check-out.
- Attendance status.
- Recorded working hours.
- Optional daily wage.
- Optional notes.

Support attendance statuses such as:

- Present.
- Absent.
- Half Day.
- Leave.

Calculate recorded hours consistently.

Provide:

- Daily attendance.
- Weekly attendance.
- Monthly attendance.
- Project-wise labour summaries.
- Worker-wise summaries.
- Labour cost summaries where wage data is available.

The prototype may simulate user roles and attendance, but must not represent attendance as independently verified or secure.

---

# 14. MATERIAL INVENTORY AND PROCUREMENT

Create a material management module.

Record:

- Material ID.
- Material name.
- Unit.
- Opening stock.
- Deliveries.
- Usage.
- Remaining stock.
- Minimum stock threshold.
- Project.
- Supplier.
- Cost.
- Date.
- Notes.

Use a consistent stock movement model.

Remaining stock = Opening stock + Deliveries − Usage.

Support:

- Material delivery records.
- Material usage records.
- Stock adjustments.
- Project-wise material tracking.
- Supplier information.
- Low-stock alerts.
- Material usage reports.
- Stock movement history.

Do not allow invalid negative stock movements without an explicit adjustment workflow.

Where material costs are included in project expenses, prevent double-counting.

---

# 15. DOCUMENTS AND PHOTOS

Create a central document management interface.

Document categories:

- Drawings.
- BOQs.
- Invoices.
- Site photos.
- Permits.
- Contracts.
- Daily reports.
- Other documents.

Support filtering by:

- Category.
- Date.
- Project.
- Construction stage.
- Work type.

Provide:

- Local document preview.
- File metadata.
- Project association.
- Version-history interface using demo data.
- Local file selection where supported.
- Export and print functionality.

For the initial prototype, local files may be previewed or exported.

Clearly explain that cloud sharing is not yet implemented and that local files are not securely stored in the cloud.

Design the storage layer so private cloud storage can be connected later.

---

# 16. REPORTS AND ANALYTICS

Create a reporting module.

Implement:

1. Project summary report.
2. Daily site report.
3. Weekly site report.
4. Monthly site report.
5. Budget versus actual report.
6. Expense breakdown.
7. Material usage report.
8. Labour attendance summary.
9. Task completion report.
10. Quotation register.
11. Invoice register.
12. Outstanding balance report.

Support:

- Project selection.
- Date range.
- Report preview.
- Print-ready layouts.
- PDF export where practical.
- CSV export where appropriate.

Show the reporting period and data source.

Clearly label demo data.

Reports must use actual application records rather than hardcoded examples.

---

# 17. TEAM AND PERMISSIONS

Design the future role structure for:

- Company Admin.
- Project Manager.
- Site Engineer/Supervisor.
- Worker.
- Architect.
- Client.

For the prototype:

- Provide a demo role switcher.
- Provide role-specific dashboards.
- Keep permission definitions in one central module.
- Use frontend visibility rules only for demonstration.

Do not treat frontend visibility rules as real security.

In the production phase, enforce permissions in the backend and database, including:

- Company-level access.
- Project-level access.
- Role-based permissions.
- Private internal notes.
- Client-facing information restrictions.

---

# 18. BUSINESS PROFILE AND SETTINGS

Create a business profile section.

Support:

- Company name.
- Logo.
- Address.
- Phone.
- Email.
- Website.
- GSTIN.
- Default currency.
- Tax preferences.
- Document numbering preferences.
- Default quotation terms.
- Default invoice terms.
- Business branding.

Use INR (₹) as the default currency.

Make currency and tax settings configurable.

Provide settings for:

- Theme.
- Date format.
- Number format.
- Data backup.
- Import and export.
- Demo data reset.
- Future integrations.

---

# 19. DATA MANAGEMENT AND BACKUPS

For the initial browser-based prototype:

- Use a versioned local data schema.
- Separate business entities into logical modules.
- Preserve data across refreshes.
- Handle malformed or missing data safely.
- Provide JSON export.
- Provide validated JSON import.
- Provide CSV exports where appropriate.
- Include a demo-data reset with confirmation.
- Warn that local data is not automatically synchronised or backed up.

Create a documented future database schema for:

- Users.
- Businesses.
- Projects.
- Clients.
- Quotations.
- Quotation items.
- Estimates.
- Estimate items.
- Change orders.
- Invoices.
- Invoice items.
- Payments.
- Expenses.
- Tasks.
- Attendance.
- Material movements.
- Site logs.
- Documents.
- Project memberships.
- Permissions.

Use unique IDs, timestamps, relationships and appropriate database constraints.

Preserve record relationships when editing or deleting data.

For destructive operations, use confirmation dialogs and appropriate dependency checks.

---

# 20. FUTURE INTEGRATIONS

Prepare clear extension points for:

- Supabase authentication.
- PostgreSQL.
- Secure cloud file storage.
- GPS-assisted attendance.
- WhatsApp notifications.
- Email notifications.
- Payment gateways.
- OCR for BOQs and invoices.
- Voice-to-text site reports.
- Drawing version comparison.
- AI-based cost forecasting.
- AI-based delay prediction.
- Advanced analytics.

Do not fake integrations.

Do not display misleading connection statuses.

Do not simulate successful external actions.

Clearly distinguish implemented features from planned integrations.

---

# 21. DEVELOPMENT PRIORITIES

Prioritise the MVP according to practical business value.

| Priority | Feature | Development priority |
|---|---|---|
| P1 | Site diary / daily logs | Essential |
| P1 | Labour attendance | Essential |
| P1 | Material tracker | Essential |
| P1 | Projects and clients | Essential |
| P1 | Estimates and quotations | Essential |
| P2 | Invoices and payment records | High |
| P2 | Tasks and deadlines | High |
| P2 | Photo uploads and documents | High |
| P2 | Client-facing progress reports | High |
| P3 | Advanced budget dashboard | Later |
| P3 | Advanced analytics | Later |
| P3 | AI cost forecasting | Future |
| P3 | AI delay prediction | Future |

The complete application may contain all planned navigation sections, but implement the core workflows properly before adding advanced features.

---

# 22. DEVELOPMENT ROADMAP

## Phase 1 — MVP

**Target duration: Approximately 3 months**

Focus on:

- Application design system.
- Dashboard.
- Projects.
- Clients.
- Daily site diary.
- Labour attendance.
- Material management.
- Tasks.
- Estimates.
- Quotations.
- Local persistence.
- Basic reports.

Goal: Deliver a usable construction management and commercial management prototype.

## Phase 2 — Commercial and client management

**Target duration: Approximately 2 months**

Focus on:

- Invoices.
- Payment records.
- Change orders.
- Project budgets.
- Expenses.
- Client portal.
- Photo uploads.
- Document management.
- Professional PDF reports.
- Secure multi-user architecture.

Goal: Make ProSite useful for managing the commercial and operational lifecycle of real projects.

## Phase 3 — Intelligence and automation

**Target: Ongoing**

Explore:

- AI-based cost forecasting.
- Delay prediction.
- OCR for BOQs and invoices.
- Voice-based site reporting.
- WhatsApp automation.
- GPS-assisted attendance.
- Advanced analytics.
- Drawing comparison.

Goal: Develop ProSite into a more intelligent construction business management platform.

These durations are planning estimates, not guaranteed delivery deadlines.

---

# 23. TESTING AND QUALITY ASSURANCE

Test the application thoroughly.

## Financial tests

- Monetary calculations and rounding.
- Quotation totals.
- Tax calculations.
- Discounts.
- Accepted quotation conversion.
- Original quotation preservation.
- Change-order calculations.
- Budget variance.
- Invoice balances.
- Multiple payments against invoices.
- Outstanding balance calculations.

## Operational tests

- Material stock movements.
- Attendance calculations.
- Task status changes.
- Daily log editing.
- Progress calculations.
- Project relationships.
- Linked expense records.

## Data tests

- Data persistence across refreshes.
- JSON export.
- JSON import validation.
- Malformed data handling.
- Duplicate IDs.
- Editing linked records.
- Deleting linked records.
- Demo data reset.

## UI tests

- Mobile layouts.
- Desktop layouts.
- Navigation.
- Search and filters.
- Empty states.
- Error handling.
- Form validation.
- Print/PDF output.
- Dark mode.

Do not declare the MVP complete until the core workflows work and major errors have been resolved.

---

# 24. DEVELOPMENT APPROACH

Build the application in stages.

**Stage 1:** Design system, navigation, dashboard and demo data.

**Stage 2:** Projects, clients, estimates, quotations and document conversion.

**Stage 3:** Site logs, tasks, attendance and materials.

**Stage 4:** Expenses, budgets, invoices, payment records and cost reports.

**Stage 5:** PDF exports, responsive testing, local persistence and data backups.

For every stage:

1. Implement the functionality.
2. Test the workflow.
3. Fix errors.
4. Check connected data.
5. Verify calculations.
6. Confirm responsive behaviour.
7. Continue to the next stage.

Do not stop after generating a visual dashboard.

Do not generate superficial buttons that have no functionality.

Do not create unnecessary placeholder pages and claim the features are complete.

If a feature cannot be implemented in the current environment, clearly identify the limitation and provide the next implementation step.

---

# 25. FINAL DELIVERABLES

At completion, provide:

1. A working ProSite application.
2. A clear project folder structure.
3. Setup and run instructions.
4. A list of implemented features.
5. A list of unimplemented features.
6. Test results.
7. Known limitations.
8. Instructions for publishing.
9. Data backup and recovery instructions.
10. A roadmap for adding secure cloud functionality.
11. A documented database schema.
12. A migration plan from browser storage to PostgreSQL.

---

# 26. FINAL PRODUCT PRINCIPLE

ProSite must become a connected construction business management platform, not simply a project dashboard or quotation generator.

Its core strength should be the connection between:

**Commercial Management + Construction Site Operations + Financial Control + Project Documentation.**

QuoteFlow should function as an integrated commercial module, not a separate disconnected application.

Prioritise a coherent, connected, working MVP over a large number of superficial features.

Build for the real working conditions of Indian construction SMEs: practical workflows, simple interfaces, reliable calculations, mobile usability and affordable implementation.

The long-term objective is to develop ProSite into a scalable SaaS product under **M and S Construction Tech**.
