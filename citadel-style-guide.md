# CITADEL Style Guide and Module Color System

_Updated: 2026-07-02_

> **Canonical visual reference:** See `citadel-design-language.html` for rendered component previews, interactive examples, and the complete design manual with all 19 sections. This markdown file is the concise specification; the HTML manual is the definitive implementation reference.

## 1. Purpose

This guide defines the visual language, color system, UI structure, and module-specific interaction rules for CITADEL and its major product surfaces:

- **CITADEL Core**: the parent platform, tenant shell, governance layer, NEPZA/regulator workspace, cross-module dashboards, audit, administration, and executive command.
- **SPINE**: the Spatial Intelligence Engine for baselines, parcels, zoning, roads, utility corridors, current reality, legal plan layers, and spatial evidence.
- **BDCE**: the Building Development Control Engine for model checking, building facts, ePlanCheck-style review, rule evidence, statutory review, and permit decision support.
- **CMS**: the Construction Management System for work programs, contractors, site reports, milestones, stage certification, completion, and handoff.
- **Citi Utility Manager**: the post-infrastructure property, tenant, owner, manager, dues, billing, utility, service charge, meter, payment, receipt, and service portal.

This is a product design system, not a marketing palette. The goal is to make complex urban governance work easier to scan, explain, operate, and audit.

## 2. Executive Design Thesis

CITADEL should feel like a **sovereign city operating console**: precise, evidence-led, modular, map-aware, official, and modern. It should not feel like a generic SaaS dashboard, a colorful consumer finance app, or a decorative smart-city brochure.

The design system has one shared shell and five visual contexts:

1. **CITADEL Core** gives the system authority and institutional trust.
2. **SPINE** makes land, baseline, and geospatial evidence immediately recognizable.
3. **BDCE** marks building-code, permit, BIM/model, and technical review work.
4. **CMS** marks site execution, construction progress, certification, and handoff work.
5. **Citi Utility Manager** marks service, utility, billing, metering, payment, and resident/property account work.

The shared rule:

> Module colors identify **where the user is working**. Semantic colors identify **what state something is in**.

This prevents the common failure where green means both "SPINE" and "success", orange means both "CMS" and "warning", or blue means both "utility" and "information".

## 3. Source Benchmarks and What CITADEL Takes From Them

| Source | Direct reference | CITADEL interpretation |
| --- | --- | --- |
| Esri Calcite Design System | <https://developers.arcgis.com/calcite-design-system/foundations/colors/> | Calcite says sparse color helps prioritize content/actions in complex map workflows. CITADEL applies this by keeping the shell neutral and using module color only for active context, selected layers, and key actions. |
| GOV.UK Design System | <https://design-system.service.gov.uk/styles/colour/> | GOV.UK separates functional colors and requires WCAG AA contrast. CITADEL applies this by separating semantic status colors from module identity colors and documenting contrast rules. |
| Microsoft Fluent 2 | <https://fluent2.microsoft.design/color> | Fluent separates neutral, shared, brand, and semantic palettes. CITADEL applies this with neutral shell tokens, module tokens, and semantic state tokens. |
| Atlassian Design System | <https://atlassian.design/foundations/color> | Atlassian defines color roles and warns against using accent colors for semantic meaning. CITADEL applies this by treating module colors as context accents only. |
| Procore CORE Design System | <https://core.procore.com/10.8.0/web/style/scss/colors/> | Procore's construction context uses HSL ladders by hue and lightness. CITADEL applies this to create module ladders with base, hover, soft, mist, border, and surface roles. |
| CORENET X | <https://info.corenet.gov.sg/overview/about-corenet-x/overview-of-corenet-x> | CORENET X emphasizes openBIM, automated model checking, BIM viewers, coordinated model review, and inter-agency collaboration. BDCE should visually support model checking, rule evidence, comparison, and coordinated response. |
| buildingSMART BCF | <https://www.buildingsmart.org/standards/bsi-standards/bim-collaboration-format/> | BCF supports model-based comments, issue statuses, categorization, assignment, and resolution. BDCE and CMS issue/comment components should use object-linked evidence, assignment, and resolution patterns. |
| buildingSMART IFC | <https://technical.buildingsmart.org/standards/ifc/> | IFC is the open standard for describing built assets. BDCE file, model, and evidence views should treat IFC as first-class, not just another upload. |
| OGC Urban Digital Twins | <https://docs.ogc.org/dp/24-025.html> | OGC links CityGML, CityJSON, MUDDI, GeoPose, SensorThings, and urban digital twin uses such as planning, BIM, 3D cadastre, facility management, energy, traffic, and environmental simulation. SPINE and Citi Utility Manager should support layered, standards-aware geospatial and utility evidence. |

## 4. Color System Principles

### 4.1 Why the First Palette Needed Revision

The first palette was accessible, but too muted. SPINE green, CITADEL civic green, and Utility aqua lived too close together emotionally. BDCE indigo did not feel technical enough when placed beside the other hues. CMS amber was safe but too quiet for construction and stage certification.

The revised palette increases hue separation and domain meaning while preserving contrast:

- SPINE moves to a vivid emerald, tied to land, baseline, ecology, and geospatial evidence.
- BDCE moves to regulatory violet, tied to technical review, rule interpretation, and permit control.
- CMS moves to safety orange, tied to construction activity, site progress, and certification.
- Citi Utility Manager moves to civic azure, tied to water, power, service continuity, and billing flow.
- CITADEL Core moves to deep civic ink, anchoring all modules without competing with them.

### 4.2 Revised Core Palette

| Role | Token | Hex | HSL | Use | Contrast on white |
| --- | --- | --- | --- | --- | --- |
| Core Ink | `--citadel-core` | `#0F2437` | 209, 57, 14 | Global shell, headings, top bar, official dark surfaces | 15.82 |
| Core Mist | `--citadel-surface-mist` | `#EAF0F5` | 206, 31, 92 | Module mist surface for Core context | N/A |
| Page Surface | `--surface-page` | `#F5F7F4` | 90, 16, 96 | App background, document background | N/A |
| Primary Text | `--text-primary` | `#172A2F` | 193, 34, 14 | Primary body text | 14.42 |
| Muted Text | `--text-muted` | `#657579` | 191, 9, 44 | Secondary copy, placeholder text | 4.57 |
| Authority Gold Text | `--authority-gold-text` | `#8A5A00` | 39, 100, 27 | Accessible gold text, official labels | 5.93 |
| Authority Gold Accent | `--authority-gold-accent` | `#B7791F` | 36, 71, 42 | Seal accent, decorative line, certificate mark only | 3.64, accent only |

Gold rule: `#B7791F` is not safe for body text on white. It is a visual accent only. Use `#8A5A00` for readable gold text.

### 4.3 Revised Module Palette

| Module | Primary token | Hex | HSL | Why it works | Use |
| --- | --- | --- | --- | --- | --- |
| SPINE | `--module-spine` | `#007A4D` | 158, 100, 24 | Clearly green but more distinct and alive than the original earth green. Strong enough for text, focus, and map selection. | Baseline, parcels, land, zoning, spatial evidence. |
| BDCE | `--module-bdce` | `#7C2D92` | 287, 53, 37 | Separates building-control work from SPINE and utility colors. Feels technical, statutory, and review-oriented without becoming generic blue. | Rules, BIM/model review, permit evidence, technical decisions. |
| CMS | `--module-cms` | `#C2410C` | 17, 88, 40 | Construction needs motion, caution, and site energy. This orange is stronger than amber but remains AA for text on white. | Work programs, milestones, stage certification, site progress. |
| Citi Utility Manager | `--module-utility` | `#0077B6` | 201, 100, 36 | Distinct from SPINE. Connects to water, power dashboards, metering, and payment/service flow without looking like fintech decoration. | Billing, utility accounts, meters, dues, receipts, service requests. |

### 4.4 Module Color Ladders

Each module has a full ladder. Components should use role tokens, not raw hex values.

#### SPINE Ladder

| Token | Value | Use |
| --- | --- | --- |
| `--module-spine-900` | `#003824` | Dark map labels, deep header, selected layer text on soft surface |
| `--module-spine-700` | `#00643F` | Hover/pressed active state |
| `--module-spine` (600) | `#007A4D` | Primary active module color |
| `--module-spine-400` | `#2FB77F` | Chart highlight, map point emphasis |
| `--module-spine-200` | `#A8E6C9` | Selected parcel fill, soft evidence fill |
| `--module-spine-100` | `#E6F7EF` | Module mist surface |

#### BDCE Ladder

| Token | Value | Use |
| --- | --- | --- |
| `--module-bdce-900` | `#35113F` | Deep technical header, rule editor dark label |
| `--module-bdce-700` | `#622176` | Hover/pressed active state |
| `--module-bdce` (600) | `#7C2D92` | Primary active module color |
| `--module-bdce-400` | `#A855C7` | Model object highlight, secondary chart line |
| `--module-bdce-200` | `#E1B7EE` | Rule evidence fill |
| `--module-bdce-100` | `#F6E9FB` | Module mist surface |

#### CMS Ladder

| Token | Value | Use |
| --- | --- | --- |
| `--module-cms-900` | `#4A1705` | Deep stage header, site timeline labels |
| `--module-cms-700` | `#9A3412` | Hover/pressed active state |
| `--module-cms` (600) | `#C2410C` | Primary active module color |
| `--module-cms-400` | `#F97316` | Milestone accent, progress marker |
| `--module-cms-200` | `#FED7AA` | Stage card fill, construction sequence surface |
| `--module-cms-100` | `#FFF1E7` | Module mist surface |

#### Citi Utility Manager Ladder

| Token | Value | Use |
| --- | --- | --- |
| `--module-utility-900` | `#073B5C` | Deep billing header, account label |
| `--module-utility-700` | `#005F92` | Hover/pressed active state |
| `--module-utility` (600) | `#0077B6` | Primary active module color |
| `--module-utility-400` | `#28A6D6` | Meter chart, service flow accent |
| `--module-utility-200` | `#B9E6F7` | Account selection fill |
| `--module-utility-100` | `#EAF8FD` | Module mist surface |

## 5. Semantic State Palette

Semantic colors describe status and urgency. They do not describe the module.

| State | Text/Icon token | Background token | Border token | Meaning |
| --- | --- | --- | --- | --- |
| Success | `--semantic-success` | `--semantic-success-bg` | `--semantic-success-border` | Approved, passed, paid, resolved, active |
| Info | `--semantic-info` | `--semantic-info-bg` | `--semantic-info-border` | Neutral note, system info, processing |
| Warning | `--semantic-warning` | `--semantic-warning-bg` | `--semantic-warning-border` | Pending evidence, SLA risk, incomplete step |
| Danger | `--semantic-danger` | `--semantic-danger-bg` | `--semantic-danger-border` | Failed, rejected, blocked, overdue, critical conflict |
| Attention | `--semantic-attention` | `--semantic-attention-bg` | `--semantic-attention-border` | AI-assisted, discretionary review, variance/amendment route |

State rules:

- If the message says "approved", "paid", "passed", or "resolved", use success, even inside SPINE.
- If the message says "warning", "pending", "incomplete", or "SLA risk", use warning, even inside CMS.
- If the message says "information", use info, even inside Citi Utility Manager.
- If the message says "AI-assisted" or "requires discretion", use attention.
- Module badges can sit beside state badges, but they cannot replace them.

## 6. System Anatomy

CITADEL uses a shared product shell:

1. **Top bar**: tenant switcher, module switcher, global search, notifications, account.
2. **Module sidebar**: role-specific navigation, active module accent, compact sections.
3. **Primary workspace**: the working surface for maps, queues, reviews, dashboards, invoices, reports, and forms.
4. **Context rail**: evidence, comments, activity, audit, approvals, payment facts, or file metadata.
5. **Command region**: primary action, export, print, share, compare, submit, approve, certify, generate invoice.

The shell changes by module only through:

- `--active-module`
- active navigation rail
- focus ring
- selected tab underline
- primary button
- selected chart series
- module badge
- selected evidence border

The shell does not change:

- base surfaces
- typography
- table structure
- semantic state palette
- audit pattern
- accessibility rules
- icon style

## 6.5 Foundation Definitions

These tokens are part of the product language, not implementation trivia. Every app should use the same shape, border, elevation, density, and focus rules before applying module color.

### 6.5.1 Border Radius

| Token | Value | Use | Do not use for |
| --- | --- | --- | --- |
| `--radius-xs` | `4px` | Tiny swatches, hex badges, table metadata, compact adornments | Cards or panels |
| `--radius-sm` | `6px` | Buttons, inputs, selected nav rows, small previews | Large marketing-style cards |
| `--radius-md` | `8px` | Evidence cards, tables, maps, workbench frames, component previews | Nested cards inside cards |
| `--radius-lg` | `12px` | Brand marks or rare high-emphasis objects | Routine panels, badges, tables |
| `999px` | pill | Status badges, module dots, small count chips | Buttons unless the product explicitly needs pill controls |

Rule: most product UI should sit between `4px` and `8px`. Large rounded rectangles quickly make CITADEL feel like a generic generated SaaS page.

### 6.5.2 Borders and Dividers

| Token | Use |
| --- | --- |
| `--border-line` | Default one-pixel neutral divider and card border |
| `--border-strong` | Input border, focused/selected neutral control border, table emphasis |
| `--active-module` | Selected evidence border, active tab underline, active workbench context only |
| semantic border tokens | Validation, warning, danger, info, attention surfaces only (`--semantic-{state}-border`) |

Rule: normal cards and page sections do not get colored borders. Color must mean selected context, evidence ownership, semantic state, or focus.

### 6.5.3 Elevation

| Token | Use |
| --- | --- |
| `--shadow-sm` | Selected rows, popovers, compact cards, component previews |
| `--shadow-md` | Workbench shells, drawers, modals, inspector overlays |
| no shadow | Page sections, dense tables, routine lists, normal documentation content |

Rule: use one elevation layer to explain hierarchy. Do not stack shadows inside nested cards.

### 6.5.4 Density and Control Heights

| Element | Height | Notes |
| --- | --- | --- |
| Badge | `20px` | Status label only, not a button |
| Compact action | `28px` | Small component-local actions |
| Standard button | `36px` | Primary/secondary command actions |
| Input | `40px` | Search, form, filter text fields |
| Touch target | `44px minimum` | Required where controls are tapped frequently |

Rule: visual size must match role. A status badge should never be as tall as an action button.

### 6.5.5 Focus and State

- Keyboard focus uses `--focus-ring`: white separation plus the active module color.
- Error text uses semantic danger, but the focus grammar stays consistent.
- Hover can change background, border, and subtle shadow; it should not change layout.
- Selected state must include more than color: label, border, stroke, icon, check, or pattern.
- Disabled state must reduce contrast and remove pointer affordance; it must not look like pending or inactive data.

## 7. Module Blueprints

### 7.1 CITADEL Core

**Primary users:** platform administrators, tenant administrators, NEPZA/regulator viewers, executives, support operators.

**Primary questions:**

- Which tenant or zone needs attention?
- Which applications, payments, inspections, or workflows are blocked?
- Which modules are healthy?
- Which decisions, baseline changes, or payments need audit review?
- What is the cross-zone or cross-tenant picture?

**Color behavior:**

- `--citadel-core` anchors the shell.
- `--authority-gold-text` marks official certifications, permit seals, executive highlights, and signed/issued document status.
- `--authority-gold-accent` is reserved for seal marks and decorative lines only.
- Gold is not used as generic warning.

**Required surfaces:**

- tenant list
- regulator dashboard
- cross-zone analytics
- audit timeline
- integration health
- user/role administration
- jurisdiction pack manager

**Anti-patterns:**

- Do not make the regulator dashboard a colorful card mosaic.
- Do not use gold as luxury decoration.
- Do not hide tenant isolation or audit state behind soft marketing language.

### 7.2 SPINE

**Primary users:** GIS officers, baseline managers, planning reviewers, spatial analysts, field verification teams, executives reviewing zone-level risk.

**Primary questions:**

- Where is this proposal?
- Which baseline version is authoritative?
- Does the proposal fit the parcel, zoning, road, drainage, utility, easement, and height context?
- Which conflict geometry proves the finding?
- How confident is the source layer?

**Color behavior:**

- Emerald marks active spatial work and selected spatial evidence.
- Baseline geometry uses solid emerald strokes.
- Proposal geometry uses dashed violet/blue or neutral strokes, depending on the related engine.
- Conflict geometry always uses danger red plus pattern/label.
- Data-confidence surfaces use neutral or semantic colors, not emerald alone.

**Required components:**

- map viewer with layer stack
- layer confidence labels
- parcel profile panel
- baseline version banner
- conflict geometry list
- spatial check result table
- map legend with non-color indicators
- evidence export

**Reference logic:**

Calcite's map-friendly color principle supports sparse module color, because map imagery and spatial layers already carry a lot of visual information. OGC's urban digital twin references support structured layer thinking: CityGML/CityJSON for 3D city context, MUDDI for underground/utility data, and SensorThings for dynamic utilities and city operations.

**Do:**

- Use color plus line type: solid for baseline, dashed for proposal, red hatch for conflict.
- Always show baseline/rule version.
- Show data confidence next to every imported layer.
- Keep map controls compact and consistent.

**Do not:**

- Use bright green fills over large map areas.
- Use green to mean pass.
- Put map legends in hidden menus.
- Treat low-confidence scanned/PDF geometry like authoritative GIS data.

### 7.3 BDCE

**Primary users:** building-control reviewers, planning reviewers, technical consultants, approving authorities, applicants responding to comments.

**Primary questions:**

- What building facts were extracted?
- Which rule failed, passed, or requires manual review?
- Which model object, floor, room, stair, lift, parking bay, or exit is implicated?
- Is the result deterministic, low-confidence, or AI-assisted?
- What should the applicant correct?

**Color behavior:**

- Regulatory Violet marks the BDCE module, selected rule, model evidence, and technical review context.
- Pass/fail badges remain semantic.
- AI or discretionary interpretation uses attention purple, not BDCE violet, unless explicitly inside a BDCE context badge.

**Required components:**

- model/BIM viewer panel
- IFC file summary
- building facts table
- rule evidence row
- rule trace drawer
- BCF-style issue/comment card
- amendment comparison view
- applicant correction builder

**Reference logic:**

CORENET X emphasizes openBIM, automated model checking, model preview, amendments comparison, and coordinated agency review. buildingSMART BCF supports model-based issue tracking: comments tied to model locations, categories, assignments, and resolution status. BDCE UI should therefore feel like a technical review workbench, not a generic file-upload page.

**Do:**

- Link every rule result to file, model object, evidence, and rule version.
- Show deterministic checks separately from AI-assisted interpretation.
- Use model-object references, not only written comments.
- Support revision comparison.

**Do not:**

- Use color alone to mark pass/fail.
- Make BDCE violet mean "info".
- Hide low-confidence extraction.
- Present AI text as official without officer review.

### 7.4 CMS

**Primary users:** project managers, contractors, stage-certification officers, inspectors, construction managers, executives.

**Primary questions:**

- What stage is the work in?
- Which milestone is late, blocked, certified, or ready for inspection?
- What evidence supports certification?
- Which contractor, inspector, or officer owns the next action?
- Is the asset ready for handoff into operations?

**Color behavior:**

- Safety Orange marks CMS context, stage timeline, selected milestone, and construction-progress accents.
- Warning yellow remains for risk/incomplete/SLA issues.
- Danger red remains for blocked/failing/unsafe states.

**Required components:**

- stage timeline
- work program Gantt/sequence strip
- milestone table
- site report cards
- inspection evidence panel
- certification decision panel
- handoff checklist
- contractor responsibility tags

**Reference logic:**

Construction systems such as Procore use stronger color ladders and operationally dense components because construction teams scan status, schedule, responsibility, cost, and evidence constantly. CMS should feel active and site-aware while still fitting the CITADEL shell.

**Do:**

- Use orange as sequence/progress identity.
- Pair every stage with evidence and owner.
- Separate "site progress" from "official certification".
- Make handoff state explicit.

**Do not:**

- Use orange as warning without a warning badge.
- Turn the whole module into a construction hazard palette.
- Hide certification conditions in notes.
- Treat photos as evidence without timestamp/source/location metadata.

### 7.5 Citi Utility Manager

**Primary users:** property owners, tenants, managers, facilities teams, billing officers, utility administrators, customer support, executives.

**Primary questions:**

- What do I owe?
- What has been paid?
- Which meter, unit, property, or account does this invoice belong to?
- Which service is active, disconnected, overdue, or under dispute?
- What is the receipt or reconciliation status?

**Color behavior:**

- Civic Azure marks utility/billing context, account selection, meter charts, and service-flow accents.
- Paid is success green.
- Overdue is danger red.
- Pending reconciliation is warning.

**Required components:**

- account/unit selector
- invoice table
- meter reading chart
- receipt panel
- dues/service charge breakdown
- payment status timeline
- arrears notice
- service request list

**Reference logic:**

Utility management needs clarity over decoration. Azure works because it is service-oriented and distinct from SPINE. The module should be calmer than CMS and less technical than BDCE, because some users are tenants and property managers rather than officials.

**Do:**

- Make money, due dates, account numbers, meter readings, and receipts very legible.
- Use tabular numerals.
- Show payment provider/manual confirmation source.
- Distinguish owner, manager, tenant, unit, and property roles.

**Do not:**

- Make it look like a consumer fintech app.
- Use aqua to mean paid.
- Hide arrears logic.
- Mix utility account identity with property ownership identity.

## 8. Component System

### 8.1 Navigation

Navigation has three layers:

1. **Global platform navigation**: CITADEL Core, tenant, search, notifications.
2. **Module navigation**: SPINE/BDCE/CMS/Utility-specific functions.
3. **Work item navigation**: tabs inside an application, parcel, model, project, invoice, or inspection.

Rules:

- Active global module uses the module color.
- Active item uses a left rail or underline, not a large filled block.
- Disabled items use neutral muted text and remain visibly disabled.
- Sidebar labels should be concrete: "Baseline layers", "Rule results", "Stage certificates", "Invoices", not generic "Management".

### 8.2 Buttons

Button role matrix:

| Button type | Color | Use |
| --- | --- | --- |
| Primary | Active module | One main module-context action in a workspace |
| Secondary | Neutral | Export, preview, save draft, view details |
| Destructive | Danger | Delete, reject, void, suspend |
| Official issue | Core Ink or Gold Text | Issue permit, issue certificate, publish official document |
| AI action | Attention | Generate draft, explain result, summarize evidence |

### 8.3 Badges

Badge categories:

- **Context badge**: module ownership, e.g. SPINE, BDCE, CMS, Utility.
- **State badge**: status, e.g. Passed, Failed, Pending, Paid, Overdue.
- **Evidence badge**: confidence/source, e.g. High confidence, IFC, Survey, Manual.
- **Decision badge**: route, e.g. Correction, Final review, Variance route.

Badges must use text and color. Color alone is not sufficient.

### 8.4 Tables

CITADEL tables should support:

- sticky headers
- compact row density
- zebra or soft-row alternation only when it improves scanning
- pinned primary identifier
- right-aligned numbers
- date and status columns
- filter chips
- row expansion
- keyboard focus
- bulk export only when permissions allow it

### 8.5 Evidence Panels

Every evidence panel should answer:

- What generated this?
- Which module produced it?
- Which file/layer/model/rule is it tied to?
- Which version was used?
- What is the confidence?
- What human action is required?

Evidence panel minimum fields:

| Field | Example |
| --- | --- |
| Source | `IFC: tower-a-rev-03.ifc` |
| Owner | `BDCE` |
| Rule | `BDCE-HEIGHT-04` |
| Version | `Rule Pack v1.2` |
| Confidence | `High, IFC structured data` |
| Action | `Officer review required` |

### 8.6 AI-Assisted Text

AI surfaces must be visually distinct:

- **Title**: name the block as AI output, e.g. `AI draft interpretation`.
- **Status badge**: use an attention badge such as `Needs officer edit`; this is a status label, not a button.
- **Body**: plain generated text in a subdued attention surface.
- **Metadata**: show confidence, citation/source, audit state, model/rule reference, and whether the text is draft-only.
- **Actions**: if actions are available, render them as actual buttons such as `Edit draft`, `Attach evidence`, or `Send for review`.
- **Audit trace**: record who edited or accepted the draft before it can become official language.

AI copy should never look like an official issued decision until a human officer approves it.

## 9. Map, Model, and Digital Twin Styling

### 9.1 Map Layer Grammar

| Layer | Stroke | Fill | Notes |
| --- | --- | --- | --- |
| Approved baseline parcel | Solid SPINE emerald | Light emerald tint | Authoritative baseline layer |
| Proposed footprint | Dashed BDCE violet or neutral | Light violet tint | Proposal, not baseline |
| Utility corridor | Solid Utility Azure | Light azure tint | Service/infrastructure context |
| Construction zone | Solid CMS orange | Light orange tint | Active site/stage context |
| Conflict geometry | Solid danger red + hatch | Danger tint | Always semantic danger |
| Variance/amendment area | Attention purple + dot pattern | Attention tint | Requires human/legal route |
| Low confidence layer | Neutral dashed gray | Neutral tint | Must show confidence label |

### 9.2 Model Viewer Grammar

BDCE model views should show:

- model tree
- selected object
- rule evidence
- object properties
- issue/comment thread
- BCF-like status
- view snapshot
- revision comparison

CMS model/site views should show:

- stage markers
- site photos
- location stamps
- certification state
- contractor responsibility
- inspection status

### 9.3 Digital Twin Rule

Digital twin views must never become decorative flythroughs. Every visual layer must support a decision:

- approve
- return for correction
- inspect
- certify
- bill
- reconcile
- hand off
- audit

## 10. Typography and Numerals

Typography stack:

```css
--font-display: "Plus Jakarta Sans", Inter, system-ui, sans-serif;
--font-body: Inter, "Plus Jakarta Sans", system-ui, sans-serif;
--font-mono: "JetBrains Mono", "SF Mono", Consolas, monospace;
```

Rules:

- Use display scale for document titles and major platform pages only.
- Use compact headings inside dashboards, tables, sidebars, and evidence panels.
- Use tabular numerals for:
  - money
  - meter readings
  - coordinates
  - dates
  - area measurements
  - application numbers
  - rule IDs
  - invoice numbers
- Use monospace for:
  - parcel IDs
  - application IDs
  - rule IDs
  - file hashes
  - coordinates
  - API routes

## 11. Accessibility and Contrast Rules

CITADEL targets WCAG 2.2 AA:

- 4.5:1 minimum for body text.
- 3:1 minimum for large text and UI component boundaries.
- Visible focus state on every interactive control.
- 44px touch target for primary controls.
- Color must be paired with text, icon, pattern, stroke style, or label.
- Map and model evidence must have legends.
- Charts must not rely on color alone.
- Reduced motion must be respected.
- Data tables must have clear headers and keyboard focus.

Contrast notes:

- `--module-spine` `#007A4D` on white: 5.40.
- `--module-bdce` `#7C2D92` on white: 7.93.
- `--module-cms` `#C2410C` on white: 5.18.
- `--module-utility` `#0077B6` on white: 4.87.
- `--authority-gold-text` `#8A5A00` on white: 5.93.
- `--authority-gold-accent` `#B7791F` on white: 3.64 and must not be used for body text.

## 12. Writing Style

CITADEL writing must be official, plain, and specific.

Use:

- "Spatial check failed: proposal overlaps Road Reserve R-04 by 2.4m."
- "Application returned for correction."
- "Payment received. Receipt CUM-2026-004183 is available."
- "AI-assisted draft. Officer review required before issue."
- "Stage 03 certification is pending inspection evidence."

Avoid:

- "Oops, something went wrong."
- "Looks good to go!"
- "Your amazing approval journey starts here."
- "Permit approved!" with an exclamation mark.
- "AI recommends approval" without source evidence and human decision state.

## 13. Token Architecture

Use role tokens and the `data-module` attribute. Never hardcode module colors inside components.

```css
/* --- Complete token set --- */
:root {
  /* Core & Authority */
  --citadel-core: #0F2437;
  --citadel-core-800: #173653;
  --citadel-core-700: #1E486D;
  --citadel-surface-mist: #EAF0F5;
  --authority-gold-text: #8A5A00;
  --authority-gold-accent: #B7791F;
  --authority-gold-mist: #FFF4D8;

  /* Module primaries */
  --module-spine: #007A4D;
  --module-bdce: #7C2D92;
  --module-cms: #C2410C;
  --module-utility: #0077B6;

  /* Module ladders (900=darkest, 100=lightest) */
  --module-spine-900: #003824;  --module-spine-700: #00643F;
  --module-spine-400: #2FB77F;  --module-spine-200: #A8E6C9;  --module-spine-100: #E6F7EF;
  --module-bdce-900: #35113F;   --module-bdce-700: #622176;
  --module-bdce-400: #A855C7;   --module-bdce-200: #E1B7EE;   --module-bdce-100: #F6E9FB;
  --module-cms-900: #4A1705;    --module-cms-700: #9A3412;
  --module-cms-400: #F97316;    --module-cms-200: #FED7AA;    --module-cms-100: #FFF1E7;
  --module-utility-900: #073B5C;--module-utility-700: #005F92;
  --module-utility-400: #28A6D6;--module-utility-200: #B9E6F7; --module-utility-100: #EAF8FD;

  /* Semantic states */
  --semantic-success: #1A6B3F;  --semantic-success-bg: #E5F2EB;  --semantic-success-border: #A8D5BB;
  --semantic-warning: #8A5A0A;  --semantic-warning-bg: #FCF4E0;  --semantic-warning-border: #E8CB8A;
  --semantic-danger: #8C1F1F;   --semantic-danger-bg: #FBECEC;   --semantic-danger-border: #E8B8B8;
  --semantic-info: #1F4E8C;     --semantic-info-bg: #EAF1FA;     --semantic-info-border: #B7D0EE;
  --semantic-attention: #6B1F66;--semantic-attention-bg: #F4ECF3; --semantic-attention-border: #D5B8D2;

  /* Surfaces */
  --surface-page: #F5F7F4;
  --surface-paper: #FFFFFF;
  --surface-panel: #F9FBF8;
  --surface-panel-2: #EEF3EF;

  /* Text */
  --text-primary: #172A2F;
  --text-muted: #657579;

  /* Borders */
  --border-line: rgba(15, 36, 55, 0.12);
  --border-strong: rgba(15, 36, 55, 0.26);

  /* Radii */
  --radius-xs: 4px;
  --radius-sm: 6px;
  --radius-md: 8px;
  --radius-lg: 12px;

  /* Shadows */
  --shadow-sm: 0 1px 2px rgba(15,36,55,0.06);
  --shadow-md: 0 10px 28px rgba(15,36,55,0.10);

  /* Focus */
  --focus-ring: 0 0 0 2px #fff, 0 0 0 4px var(--active-module, var(--citadel-core));

  /* Fonts */
  --font-display: "Plus Jakarta Sans", Inter, ui-sans-serif, system-ui, sans-serif;
  --font-body: Inter, "Plus Jakarta Sans", ui-sans-serif, system-ui, sans-serif;
  --font-mono: "JetBrains Mono", "SF Mono", Consolas, ui-monospace, monospace;
}

/* Module context binding */
[data-module="core"]    { --active-module: var(--citadel-core); }
[data-module="spine"]   { --active-module: var(--module-spine); }
[data-module="bdce"]    { --active-module: var(--module-bdce); }
[data-module="cms"]     { --active-module: var(--module-cms); }
[data-module="utility"] { --active-module: var(--module-utility); }
```

Role tokens that components should consume (not raw hex values):

| Group | Tokens |
|---|---|
| Module context | `--active-module`, `--active-module-hover`, `--active-module-soft`, `--active-module-mist` |
| Semantic state | `--semantic-success`, `--semantic-warning`, `--semantic-danger`, `--semantic-info`, `--semantic-attention` (each has `-bg` and `-border` variants) |
| Surface | `--surface-page`, `--surface-paper`, `--surface-panel`, `--surface-panel-2` |
| Text | `--text-primary`, `--text-muted` |
| Border | `--border-line`, `--border-strong` |
| Radius | `--radius-xs`, `--radius-sm`, `--radius-md`, `--radius-lg` |
| Shadow | `--shadow-sm`, `--shadow-md` |
| Focus | `--focus-ring` |

Avoid hardcoding module colors inside components. Bind `data-module` once on the shell or body and the component adapts automatically.

## 14. Module Comparison Matrix

| Dimension | SPINE | BDCE | CMS | Citi Utility Manager |
| --- | --- | --- | --- | --- |
| Visual metaphor | land intelligence | regulatory model review | site execution | service flow |
| Primary evidence | maps, layers, geometry | model facts, rules, IFC, BCF issues | site reports, milestones, certifications | invoices, meters, accounts, receipts |
| Main user pressure | spatial accuracy | rule defensibility | schedule/certification progress | payment clarity |
| Primary color | emerald | regulatory violet | safety orange | civic azure |
| Main UI surface | map workbench | model/rule workbench | timeline/work program | account/billing portal |
| Must show | baseline version | rule/model version | stage owner | account/unit link |
| Biggest risk | confusing proposal with baseline | hiding low-confidence or AI results | confusing progress with certification | confusing due with paid |

## 15. Decision Summary

The CITADEL design system is:

- one shared operating shell
- strong module hue separation
- neutral by default
- evidence-first
- map/model/report aware
- semantic-state disciplined
- accessible before decorative
- direct about uncertainty
- official without being visually dead

The revised color system is more vivid because the modules need to be recognizable under pressure. The restraint should come from layout and token discipline, not from making every hue quiet.

## 16. Build Contract for Human and LLM Implementers

This section is the implementation grammar. It exists so a designer, engineer, or LLM can generate a CITADEL screen without guessing the design intent.

### 16.1 Generation Sequence

Follow this order before composing any screen:

1. **Identify the active module.**
   - Core, SPINE, BDCE, CMS, or Citi Utility Manager.
   - Bind `--active-module` at the shell, workbench, or page scope.
   - Do not recolor every component manually.

2. **Identify the user's job pressure.**
   - SPINE: spatial accuracy, baseline authority, layer confidence.
   - BDCE: rule defensibility, model evidence, correction routing.
   - CMS: stage progress, inspection evidence, certification state.
   - Citi Utility Manager: payment clarity, account ownership, receipt/reconciliation.
   - Core: oversight, tenant isolation, governance, audit.

3. **Separate module context from semantic state.**
   - Module color says where the user is working.
   - Semantic color says what happened.
   - A `Passed` badge is success green inside every module.
   - A `Conflict` badge is danger red inside every module.
   - `AI-assisted` or discretionary review uses attention purple.

4. **Choose the primary working surface.**
   - Use a map for spatial evidence.
   - Use a model/rule workbench for BDCE.
   - Use a timeline/table/checklist for CMS.
   - Use account/payment rows for utilities.
   - Use evidence cards for any result that affects approval, certification, payment, routing, or audit.

5. **Attach provenance before visual polish.**
   Every decision-bearing object must show:
   - source
   - owner
   - version
   - confidence
   - status
   - next action
   - audit state where applicable

6. **Apply foundation tokens.**
   - `4px` radius for micro tokens.
   - `6px` radius for controls and compact inputs.
   - `8px` radius for cards, tables, workbench frames, and evidence panels.
   - `12px` radius only for rare high-emphasis objects or brand marks.
   - Default borders are neutral one-pixel lines.
   - Badges are 20px, compact actions 28px, standard buttons 36px, inputs 40px, touch targets at least 44px.

7. **Validate non-color meaning.**
   - Map layers need stroke, fill, pattern, label, and legend.
   - Status needs text plus semantic color.
   - Selected items need color plus border, check, icon, position, or label.
   - AI text needs draft state and audit metadata.

### 16.2 Component Anatomy Contract

| Component | Required anatomy | Token rule | Never do this |
| --- | --- | --- | --- |
| Button | Action verb, one dominant primary per region, focus, disabled state | Primary uses active module; destructive uses danger; official issuing uses Core Ink | Use danger for normal primary action or make status text look like a button |
| Status badge | 20px tag, explicit label, semantic color | State wins over module | Use module color as success/warning/danger |
| Evidence card | Finding title, semantic status, source, owner, version, confidence, next action | Module accent identifies owner; semantic badge identifies result | Show conclusion without provenance |
| Map layer | Name, stroke, fill/pattern, legend row, label, confidence | Baseline solid SPINE; proposal dashed; conflict danger hatch | Rely on fill color only |
| AI draft | AI title, draft status badge, generated body, citation, confidence, audit, real actions | Attention surface; actions are buttons; review requirement is a badge | Present AI output as official or write review requirement as loose text |
| Payment row | Account/unit, charge, amount, receipt/source, reconciliation state | Utility marks ownership; paid/reconciling/overdue are semantic | Hide receipt, source, or manual confirmation |
| Data table | Pinned ID, status, owner/source, updated date, next action, expandable evidence | Neutral rows, semantic badges, selected module accent only | Convert dense operational data into a decorative card mosaic |

### 16.3 Screen Construction Patterns

For any new CITADEL screen, use this structure unless the workflow proves otherwise:

1. **Shell**
   - Top bar with tenant/module/global actions.
   - Module context visible but not dominant.
   - Search/filter where repeated work requires it.

2. **Workspace**
   - The largest surface is the user's main task: map, model, table, form, timeline, payment list, or evidence queue.
   - Avoid landing-page hero composition inside operational tools.
   - Use compact headings and dense but readable rows.

3. **Context rail or evidence panel**
   - Show source, version, owner, confidence, comments, audit, or next action.
   - Do not hide evidence in a modal if the user needs it to decide.

4. **Command region**
   - One primary action.
   - Secondary actions are quiet.
   - Destructive actions are semantic danger.
   - Official issue/approve/certify actions use Core Ink or a clearly official treatment.

5. **Audit path**
   - Approval, certification, payment, AI draft acceptance, baseline amendment, and rule override states need durable logs.

### 16.4 LLM Prompt Contract

When asking an LLM to generate CITADEL UI, include this instruction:

> Build a restrained civic operations interface for CITADEL. Use neutral surfaces, compact medium-weight typography, and one active module token. Separate module identity from semantic state. Use evidence-first components with source, owner, version, confidence, status, next action, and audit state. Do not use colored card borders, heavy pills, marketing hero sections, generic dashboard mosaics, or AI text that looks like an issued decision. For maps, use stroke, pattern, labels, and legend. For payments, show account, amount, receipt, source, and reconciliation state. For AI drafts, show title, attention status badge, citation, confidence, audit state, and real action buttons.

### 16.5 Quality Gate Before Delivery

Before a screen or component is accepted, answer yes to all:

- Can the user identify the active module in two seconds?
- Can the user identify the semantic state without relying on color alone?
- Does every decision-bearing result show source, version, confidence, owner, and next action?
- Are badges visibly smaller than buttons?
- Are ordinary cards bordered neutrally, without decorative module borders?
- Are map conflicts hatched, labeled, and represented in the legend?
- Is AI output clearly draft/assistive until human approval?
- Is official issuing visually distinct from normal workflow actions?
- Does mobile preserve labels and avoid horizontal overflow?
- Would the UI still feel professional if all nonessential shadows were removed?

---

## 17. Icon System

See the HTML manual (section 12) for rendered examples.

**Sizes:** 16px inline (status dots, table icons), 20px control (button icons, nav), 24px standalone (tabs, empty states).

**Rules:**
- Use one icon family with consistent stroke weight across all modules.
- Icon-only buttons require tooltips.
- Icons support scanning but never replace text labels for critical information.
- Map layer icons must be accompanied by a text label in the legend.
- Use `--text-muted` for inactive icons, `--text-primary` for active, module color for selected.
- Never use semantic colors for icons unless the icon *is* a state indicator (warning triangle, error X, success check).

## 18. Navigation and Hierarchy

CITADEL has three navigation layers. They must not be mixed:

| Layer | Location | Scope | Behaviour |
|---|---|---|---|
| Global shell | Top bar | Tenant, module selector, global search, notifications, account | Switching modules navigates to the module's default workspace |
| Module navigation | Left sidebar | Module functional areas (layers, baselines, conflicts, reports) | Persistent within a module session; uses `--active-module` accent |
| Work item | Tabs / breadcrumbs / steps | Single permit, parcel, invoice, inspection | Nest inside module; close without affecting module context |

**Breadcrumbs:** Use when depth > 2 (e.g., SPINE > Parcels > CC-A-104 > Conflicts). Position above workspace heading. Active leaf uses `--text-primary`, ancestors use `--text-muted`.

**Anti-patterns:** No mega-menus, flyouts, or hamburger menus for frequently accessed module functions. No module-level navigation inside page-level tabs.

## 19. Drawers, Dialogs, and Side Panels

See the HTML manual (section 14) for the full decision matrix and specifications.

| Pattern | When to use | Key spec |
|---|---|---|
| **Drawer** | User needs to reference the main view (evidence details, rule traces, issue threads, AI draft review) | 480px standard / 640px wide, slides from right via transform, 200ms ease-out, focus trapped, backdrop click-to-close |
| **Dialog** | Quick decision with no external reference needed (confirmations, one-step approvals, short forms, destructive actions) | 420px standard / 560px wide, centred overlay with scrim, 120ms ease-in, no X on destructive dialogs |
| **Side Panel** | Persistent context that updates on selection (audit trail, layer properties, account summary) | 320px right rail, collapsible, reflows main content, no overlay |

**Decision flow:** Need to see main view? → Drawer or side panel. Quick confirmation? → Dialog. Persistent context? → Side panel. Destructive action? → Dialog with explicit buttons, no X close.

## 20. Notifications and Alerts

| Surface | Position | Duration | Use for |
|---|---|---|---|
| Toast | Top-right, stacked | 3s auto-dismiss (except errors) | Save confirmations, action success, non-critical errors |
| Banner | Top of workspace, below header | Persistent until resolved | SLA warnings, system notices, data version changes |
| Inline callout | Inside card, form, or section | Persistent while condition exists | Validation errors, field-level warnings, semantic token triples |
| Badge | On nav items, table rows, tabs | Persistent count | Pending items, unread evidence, open corrections |

**Toast spec:** Slide in 180ms, 8px stack gap, hover pauses auto-dismiss, never auto-dismiss danger/error toasts, 4px left border for semantic indicator.

## 21. Form Patterns

**Core rules:**
- Single-column layout for operational forms. Multi-column causes scanning errors.
- Labels always visible. Placeholder text is never a substitute for a label.
- Required fields use a danger asterisk (`color: var(--semantic-danger)`).
- Errors appear below the field (not on blur alone), using `--semantic-danger`.
- 40px input height, neutral `--border-strong` at rest, module focus ring on active.

**Field types:**
- Text input: for IDs, references, names.
- Select: for controlled choices (jurisdiction, role, status). Group long option lists.
- Date picker: text input with `type="date"` or structured inputs. Always show format.
- File upload: drop zone with name, size, type, progress. IFC files get model preview thumbnail.
- Radio / checkbox: vertical alignment for scanability, 44px touch target, fieldset + legend.
- Textarea: 3 rows minimum, character count for limits, monospace for structured data.

**Multi-step forms:** Step indicator at top (numbered, module accent for current, check for completed). Each step self-contained. Back navigation preserves data. Final step shows review summary.

## 22. Data Visualization

**Colour palette:**
- Primary series: `--module-{name}-400`
- Secondary series: `--module-{name}-200`
- Threshold lines: `--semantic-warning` (SLA), `--semantic-danger` (hard limit)
- Annotations: `--semantic-attention` (AI-flagged points, review-pending)
- Grid and axes: 25% opacity `--border-line` for grids, `--text-muted` for labels

**Chart types:** Bar for category comparison, line for trends over time, small multiples for zone/module comparison.

**Banned:** Pie charts with > 3 slices, radar charts, 3D charts, donut charts that look like progress indicators.

**Accessibility:** Every chart must include an adjacent data table. Colour-coded legends must include shape/pattern differences. Provide text summaries for key insights. Chart entrance animations opt-in only (respect reduced motion).

## 23. Empty, Loading, and Error States

Every dynamic component must specify all three:

| State | When | Structure | Placement |
|---|---|---|---|
| Empty | No data exists for current view/filter/search | Illustration (optional) + heading + explanation + action button | In content area, shell/nav visible |
| Loading | Data being fetched (under 300ms = nothing, 300ms–3s = skeleton, over 3s = skeleton + progress + cancel) | Skeleton screens (table: 5-7 grey bars matching columns; cards: 3-4 blocks) | In the component's content area |
| Error | Request failed, computation errored, resource unavailable | Error icon + what happened + how to resolve + retry | Inline for component, banner for page, dialog for destructive failure |

**Error writing:** Never vague ("Something went wrong"). Be specific: "Payment verification failed. Bank returned code DECLINED-03. Check account details or try a different payment method."

## 24. Governance and Contribution

**Component lifecycle:** Proposal (document + issue) → Review (weekly, cross-module sign-off) → Approve or return (with reasons) → Implement + publish (tokens, HTML, a11y, notes) → Adopt + audit (annual review, deprecation with sunset date).

**Roles:** Design system lead (token authority, final approval), Module design owners (module advocacy, weekly attendance), Engineering (implementation, bug filing), All contributors (proposals via template, use system tokens, document exceptions).

**Exception process:** Document user need, why system is insufficient, proposed deviation, scope, and review date. Reviewed by lead + module owner. Approved exceptions have expiry dates. Expired exceptions are absorbed or retired.

**Annual audit checklist:**
- All components have ≥ 1 production implementation.
- All tokens are used (unused tokens flagged for removal).
- All contrast ratios meet WCAG 2.2 AA.
- All components have empty/loading/error/edge-case docs.
- All module colours tested against new OS/browser rendering.
- No hardcoded colours in production CSS outside `:root`.
- All exceptions from past year reviewed, resolved, or extended.

## 25. Module Integration Requirements

Every module has a distinct data domain, API surface, event stream, file-handling policy, authentication model, and deployment dependency. Use these checklists when scoping, implementing, or reviewing a module backend. No module backend ships without: a published OpenAPI spec, a health endpoint, a seed data strategy, an event contract, an idempotency policy, and a rollback plan for its first three releases.

### Shared Integration Foundations

These apply to every module before any module-specific integration begins.

| Foundation | Rule | Use |
|---|---|---|
| API gateway | All module APIs route through a shared gateway at `/api/{module}`. Handles rate limiting (1000 req/min per tenant), auth token validation, CORS, request logging, request ID propagation (`X-Request-Id`). | Gateway strips tenant context from JWT and injects `X-Tenant-Id` and `X-User-Id` headers to downstream service. |
| Health endpoint | `GET /api/{module}/health` returns `{ status: "ok", version, uptime, dependencies: { db, cache, queue, external_api } }`. Runs every 30s from gateway. | Gateway drops routes returning non-200. Dependencies list must include every external service the module calls. |
| Observability | Structured JSON logging to stdout. Trace ID via `X-Request-Id`. Metrics at `GET /api/{module}/metrics` (request count, latency p50/p95/p99, error rate, pool usage). | Prometheus scrape target. Logs via fluentd. Dashboard per module. |
| Idempotency | All POST/PUT/PATCH/DELETE accept `Idempotency-Key` header (UUID v4). Duplicates within 24h return original response with `Idempotent-Replayed: true`. | Payment capture, permit issuance, document upload, status transitions. Keys stored with TTL in Redis. |
| Error contract | All errors return `{ error: string, detail: string, errors?: Record<string, string[]> }`. Statuses: 400, 403, 404, 409, 422, 500, 503. | 422: `{ "error": "Validation failed", "detail": "3 fields require attention", "errors": { "email": ["Enter a valid email address"] } }` |
| Pagination | List endpoints accept `?page, per_page, sort, filter[key]=value`. Response: `{ data: [], total, filtered_total, page, per_page, sort }`. Max per_page 100, default 20, default sort `updated_at:desc`. | `GET /api/spine/parcels?page=2&per_page=50&sort=reference:asc&filter[status]=valid` |
| Authentication | JWT bearer via `Authorization: Bearer {token}`. Token: `{ sub, tenant_id, roles[], module_access[] }`. Gateway validates. Module services trust `X-User-Id` and `X-Tenant-Id`. | Roles: `admin`, `officer`, `reviewer`, `inspector`, `applicant`, `contractor`, `tenant_owner`, `viewer`. |
| File handling | Files uploaded to shared object store before form submission. `POST /api/{module}/upload` returns `{ file_id, name, size, type, url, thumbnail_url }`. Max 50MB. Accepted: .pdf, .ifc, .dxf, .gml, .dwg, .png, .jpg, .geojson, .docx, .xlsx. | Upload IFC to /api/bdce/upload, then submit permit with file_id. Files scanned for malware before storage. |
| Events and SSE | Modules emit events to shared bus. Events: `{ id, type, source, timestamp, data, tenant_id, user_id }`. Frontend subscribes via SSE at `GET /api/{module}/events`. | Types: `resource.created`, `resource.updated`, `status.changed`, `payment.received`, `rule.evaluated`, `inspection.completed`. |
| Database | Each module has own schema on shared PostgreSQL. Migrations versioned, run as part of deployment. Rollback scripts required. Audit columns (`created_by, created_at, updated_by, updated_at`) on every table. | Schema: `citadel_{module}`. Tables: `citadel_spine.parcels`, `citadel_bdce.rules`, `citadel_cms.stages`, `citadel_utility.invoices`. |

### 25.1 CITADEL Core — Platform Shell Integration

Core provides the tenant shell, user management, authentication, audit logging, and cross-module dashboards. Every other module depends on Core for identity and tenant context.

**API Endpoints**

| Method | Path | Purpose | Auth |
|---|---|---|---|
| GET | `/api/core/tenants` | List tenants (zones, LGAs, development areas) | admin |
| POST | `/api/core/tenants` | Provision a new tenant with schema and initial admin user | super_admin |
| GET | `/api/core/users` | List users, filterable by role and status | admin |
| POST | `/api/core/users/invite` | Invite user via email, assigns role and module access | admin |
| PATCH | `/api/core/users/{id}/roles` | Update user role or module access scopes | admin |
| GET | `/api/core/audit-log` | Paginated audit trail, filterable by user, action, resource, date range | admin, reviewer |
| GET | `/api/core/dashboard` | Cross-module summary: counts by status, SLA breaches, pending items | admin, viewer |
| GET | `/api/core/modules` | List available modules and their health status | authenticated |
| GET | `/api/core/notifications` | User notifications (unread count, paginated list) | authenticated |
| POST | `/api/core/notifications/{id}/read` | Mark notification as read | authenticated |

**Pre-Integration Checklist**
- Identity provider configured (Keycloak, Auth0, or Azure AD) with OIDC — JWT includes `tenant_id`, `roles`, and `module_access` claims.
- Tenant provisioning automation: creating a new tenant creates its schema, seeds default roles, creates initial admin user, sends setup invitation.
- Audit log schema is append-only with 7-year retention. All state-changing operations across all modules emit audit events.
- Notification bus: Core publishes notifications consumed by all modules. Types: `action.required`, `status.change`, `sla.warning`, `system.announcement`.
- Cross-module dashboard aggregates from each module's analytics endpoint. Each module exposes `GET /api/{module}/analytics/summary` returning `{ total, by_status[], sla_breaches, pending }`.
- RBAC policy defined for every module endpoint. Core provides role definitions; each module defines its own permission matrix.
- Session management: tokens expire after 8h, refresh tokens after 30d. Concurrent session limit: 5 per user. Idle session timeout: 30min.
- MFA required for admin and super_admin roles (TOTP or WebAuthn). MFA enrollment forced on first login.
- Data export: all modules support tenant-level data export (JSON + CSV) via admin API. Exports run asynchronously with notification on completion.

**Data Model Requirements**

| Entity | Required fields | Relationships | Notes |
|---|---|---|---|
| Tenant | id, name, code, jurisdiction, status, settings (JSONB), created_at | has_many users, has_many audit_logs | `code` is URL-safe slug. `settings` includes locale, timezone, currency, feature flags. |
| User | id, tenant_id, email, name, roles[], module_access[], status, mfa_enrolled | belongs_to tenant, has_many notifications | `module_access` controls which module UIs are visible and which endpoints return non-403. |
| Audit Log | id, tenant_id, user_id, action, resource_type, resource_id, changes (JSONB), ip_address, user_agent, created_at | belongs_to tenant, belongs_to user (optional) | Append-only. Actions: `created, updated, deleted, viewed, exported, status_changed, login, logout, mfa_enrolled`. |
| Notification | id, tenant_id, user_id, type, title, body, resource_type, resource_id, read_at, created_at | belongs_to user | Types: `action.required`, `status.change`, `sla.warning`, `system.announcement`. |

**Deployment Dependencies**
- Runtime: Node.js 20+ or Go 1.22+ (high I/O for auth and event streaming; Go preferred for gateway).
- Database: PostgreSQL 15+ with pgcrypto extension. Separate schema per tenant. Pool: min 5, max 20.
- Cache: Redis 7+ (sessions 8h TTL, idempotency 24h, rate limiter 1min sliding window).
- Object store: S3-compatible (MinIO, AWS S3, DO Spaces). Prefix: `/{tenant_id}/{module}/`.
- Message queue: Redis Streams or RabbitMQ for event bus and SSE fan-out.
- External: OIDC provider, SMTP gateway, SMS gateway (optional).

### 25.2 SPINE — Spatial Intelligence Engine Integration

SPINE manages baseline parcels, zoning layers, roads, utility corridors, spatial evidence, and map tile serving. It is the geospatial foundation that every other module references.

**API Endpoints**

| Method | Path | Purpose | Auth |
|---|---|---|---|
| GET | `/api/spine/parcels` | List parcels with pagination, filter by zone, status, owner | authenticated |
| GET | `/api/spine/parcels/{id}` | Single parcel with geometry, version history, linked documents | authenticated |
| POST | `/api/spine/parcels` | Create parcel with GeoJSON geometry, attributes, source file reference | officer, admin |
| PATCH | `/api/spine/parcels/{id}` | Update parcel attributes or geometry (creates new version) | officer, admin |
| GET | `/api/spine/layers` | List available map layers with visibility, source, updated_at | authenticated |
| PATCH | `/api/spine/layers/{id}` | Toggle layer visibility, update style | authenticated |
| GET | `/api/spine/tiles/{z}/{x}/{y}` | Map tile serving (vector tiles for parcels, aerial, street) | authenticated |
| GET | `/api/spine/baselines` | List baseline versions with status (draft, current, superseded) | authenticated |
| POST | `/api/spine/baselines` | Publish new baseline version from uploaded geometry | admin |
| GET | `/api/spine/conflicts` | List spatial conflicts between proposal and baseline layers | reviewer, admin |
| GET | `/api/spine/analytics/summary` | Module dashboard summary | authenticated |

**Pre-Integration Checklist**
- PostGIS extension enabled and configured. All spatial queries use indexed geometry columns (GIST on `geometry(Geometry, 4326)`).
- Vector tile pipeline: parcels and layers served as MVT from `/{z}/{x}/{y}` with CDN-level cache and 1h TTL.
- Version-controlled geometry: every parcel update creates a new version. UI can diff between versions. Baseline publication locks current version.
- CRS: WGS 84 (EPSG:4326) for API storage, EPSG:3857 for tile serving. API inputs/outputs use GeoJSON with CRS84.
- Layer stacking order: baseline parcels → zoning → roads → utility corridors → proposals → conflicts. Each layer has Z-index, label visibility, min/max zoom.
- Conflict detection engine: compares proposal geometry against baselines, produces conflict records with geometry, type (overlap, encroachment, boundary violation), severity.
- Data confidence labels: every imported layer stores `confidence` field (high: surveyed, medium: digitised from orthophoto, low: scanned PDF).
- Baseline publication workflow: draft → under review → current. Superseded baselines remain readable.
- Export: `GET /api/spine/parcels/export` returns GeoJSON or Shapefile. Large exports run asynchronously.
- Supported import formats: GeoJSON, Shapefile (ZIP), DXF, GML, CSV with WKT geometry.

**Data Model Requirements**

| Entity | Required fields | Spatial index | Notes |
|---|---|---|---|
| Parcel | id, tenant_id, reference, geometry (MultiPolygon), area_sqm, zone, status, owner, confidence, source_file, version, baseline_id, created_at, updated_at | Yes (geometry) | `reference` is human-readable ID. `status`: active, pending, superseded, historical. |
| Layer | id, tenant_id, name, type, geometry_type, visible, z_index, min_zoom, max_zoom, stroke_style, fill_color, source, confidence, updated_at | No | `type`: baseline, zoning, road, utility, proposal, conflict. Style fields map to CSS paint rules. |
| Baseline | id, tenant_id, version, status, published_by, published_at, notes, superseded_by | No | `status`: draft, current, superseded. Version auto-increments per tenant. |
| Conflict | id, tenant_id, parcel_id, layer_id, geometry, type, severity, status, rule_id, created_at | Yes (geometry) | `type`: overlap, encroachment, boundary_violation, setback. Severity: critical, moderate, advisory. |

**Deployment Dependencies**
- Runtime: Python 3.11+ with GeoDjango (spatial processing) or Go with tile serving libs.
- Database: PostgreSQL 15+ with PostGIS 3+. GIST indexes on all geometry columns. ST_AsMVT for vector tiles.
- Tile cache: CDN or reverse proxy (Cloudflare, Varnish, Nginx). TTL: 1h baselines, 5min proposals.
- Background jobs: Celery (Python) or Redis Streams for import, conflict detection, export.
- External: DEM API (optional), aerial/satellite tile provider.

### 25.3 BDCE — Building Development Control Engine Integration

BDCE manages BIM/model checking, building facts extraction, rule engine evaluation, permit review, correction routing, and amendment comparison. Most technically complex module.

**API Endpoints**

| Method | Path | Purpose | Auth |
|---|---|---|---|
| GET | `/api/bdce/applications` | List permit applications, filter by status, type, applicant | authenticated |
| POST | `/api/bdce/applications` | Submit new permit application with model reference and documents | applicant, officer |
| GET | `/api/bdce/applications/{id}` | Full application detail | authenticated |
| PATCH | `/api/bdce/applications/{id}/status` | Transition application status | officer, admin |
| GET | `/api/bdce/models` | List uploaded IFC/BIM models | authenticated |
| POST | `/api/bdce/models` | Upload IFC model (triggers fact extraction + rule evaluation) | applicant, officer |
| GET | `/api/bdce/models/{id}/facts` | Building facts extracted from IFC | authenticated |
| GET | `/api/bdce/rules` | List rule packs and individual rules | reviewer, admin |
| POST | `/api/bdce/rules/evaluate` | Trigger rule evaluation for an application | officer, admin |
| GET | `/api/bdce/results` | Rule evaluation results with status per rule | authenticated |
| POST | `/api/bdce/results/{id}/accept` | Accept or override a rule result | officer, admin |
| GET | `/api/bdce/corrections` | List corrections with status, assignment, due date | authenticated |
| POST | `/api/bdce/corrections/{id}/respond` | Submit correction response | applicant |
| GET | `/api/bdce/analytics/summary` | Module dashboard summary | authenticated |

**Pre-Integration Checklist**
- IFC parsing pipeline: dedicated service (IfcOpenShell or xBIM Toolkit) extracts storeys, spaces, elements, properties, quantities, relationships. Parsing async with SSE progress updates.
- Rule engine (separate service): evaluates rules against extracted building facts. Each rule: name, description, category, severity, evaluation logic, documentation. Returns passed/failed/error/manual-review with evidence.
- Rule pack versioning: packs have lifecycle draft → active → deprecated → retired. Active packs used for all new evaluations.
- Model version comparison: delta evaluation only for new model versions. UI shows colour-coded diff highlights.
- Correction workflow: type (plan, model, document), assignment, due date, status (open, in-progress, resolved, rejected), linked evidence.
- AI-assisted interpretation: AI results marked ("AI draft" label, confidence score, citation). Never final without officer acceptance.
- Amendment comparison: side-by-side diff of application fields, model data, rule results. History preserved as DAG.
- BCF integration: issues exportable as BIM Collaboration Format. Imported BCF links to model objects with viewpoint and comment thread.
- Application status machine: draft → submitted → under review → correction required → resubmitted → approved / rejected → issued → void.
- Performance SLA: model parsing under 30s for 500MB IFC. Rule evaluation under 10s per pack. SSE progress every 5s.

**Data Model Requirements**

| Entity | Required fields | Relationships | Notes |
|---|---|---|---|
| Application | id, tenant_id, reference, type, status, applicant_id, parcel_id, model_id, description, submitted_at, issued_at, status_history (JSONB) | belongs_to parcel (SPINE), has_many models, results, corrections | `type`: new_construction, renovation, demolition, variance, amendment. |
| Model | id, tenant_id, application_id, version, file_id, file_name, file_size, file_hash, parsed_status, parsed_at, storeys (JSONB), facts (JSONB) | belongs_to application, has_many results | `parsed_status`: pending, parsing, complete, failed. `facts` contains extracted building params. |
| Rule | id, tenant_id, pack_id, code, name, category, severity, version, logic, status, documentation | belongs_to rule_pack, has_many results | `code` is unique ID (e.g., BDCE-HEIGHT-04). Severity: error, warning, info, manual_review. |
| Rule Result | id, tenant_id, application_id, model_id, rule_id, status, detail, evidence_refs (JSONB), confidence, accepted_by, accepted_at, accepted_notes | belongs_to application, rule, model | `status`: passed, failed, manual_review, not_evaluated, overridden. |
| Correction | id, tenant_id, application_id, type, status, assigned_to, due_date, description, response, created_at, resolved_at | belongs_to application, has_many documents | `type`: plan, model, document, fee. Status: open, in_progress, resolved, rejected. |

**Deployment Dependencies**
- Runtime: Python 3.11+ (rule engine, IFC parsing). Go or Laravel (API layer).
- Database: PostgreSQL 15+ with JSONB. GIN indexes on JSONB fields.
- Queue: Redis Streams or RabbitMQ for model parsing and rule evaluation (dedicated queues with priority).
- Object store: S3-compatible. Prefix: `/{tenant_id}/bdce/models/{application_id}/`.
- External: SPINE API (parcel context), CMS API (optional construction stage integration).

### 25.4 CMS — Construction Management System Integration

CMS manages construction work programs, stage gates, site inspections, milestone certification, contractor management, and asset handoff.

**API Endpoints**

| Method | Path | Purpose | Auth |
|---|---|---|---|
| GET | `/api/cms/projects` | List construction projects, filter by status, contractor, stage | authenticated |
| POST | `/api/cms/projects` | Create new project from approved permit or manually | officer, admin |
| GET | `/api/cms/projects/{id}` | Project detail with stage timeline, milestones, reports | authenticated |
| PATCH | `/api/cms/projects/{id}/status` | Update project status | officer, admin |
| GET | `/api/cms/stages` | List stage definitions for project or jurisdiction | authenticated |
| GET | `/api/cms/stages/{id}` | Stage detail with gate criteria, evidence requirements | authenticated |
| PATCH | `/api/cms/stages/{id}/status` | Transition stage status | officer, inspector |
| POST | `/api/cms/stages/{id}/certify` | Certify stage completion | officer, admin |
| GET | `/api/cms/inspections` | List site inspections | authenticated |
| POST | `/api/cms/inspections` | Schedule inspection | inspector, officer |
| PATCH | `/api/cms/inspections/{id}/report` | Submit inspection report | inspector |
| GET | `/api/cms/milestones` | List milestones with planned/actual dates | authenticated |
| GET | `/api/cms/contractors` | List registered contractors | authenticated |
| GET | `/api/cms/handover/{project_id}` | Handoff checklist for completed project | officer, admin |
| POST | `/api/cms/handover/{project_id}/complete` | Complete handoff — asset record created | admin |
| GET | `/api/cms/analytics/summary` | Module dashboard summary | authenticated |

**Pre-Integration Checklist**
- Stage gate engine: each jurisdiction defines stage templates (foundation, structure, MEP, finishing, handover). Each stage has gate criteria that must be satisfied.
- Milestone tracking: milestones have planned/actual dates, status (pending, achieved, missed, re-baselined), evidence links, owner.
- Inspection workflow: scheduled against project/stage. Reports include findings, geotagged photos, evidence, outcome (pass, conditional_pass, fail, re-inspection_required).
- Certification chain: each stage certification records certifying officer, digital signature, evidence reviewed, conditions, date. Durable and auditable.
- Photo metadata: stores timestamp, GPS coordinates, device identifier, photographer. Linked to inspection findings.
- Handoff checklist: all stages certified, corrections resolved, as-built documents submitted, utility accounts created, asset register updated, warranty filed.
- Contractor registry: registration number, specialisations, insurance expiry, prequalification status, portfolio, performance score.
- Integration with BDCE: reads approved permits to create initial project. Permit conditions flow into stage gate requirements.
- Integration with SPINE: reads parcel context. Construction zone layers published to SPINE maps.
- Stage timeline: backend returns ordered stages with status, dates, evidence counts for timeline visualization.

**Data Model Requirements**

| Entity | Required fields | Relationships | Notes |
|---|---|---|---|
| Project | id, tenant_id, reference, name, permit_id, parcel_id, contractor_id, status, stage_template_id, started_at, completed_at, handover_status | belongs_to permit (BDCE), parcel (SPINE), contractor. has_many stages, inspections, milestones. | `status`: planned, active, on_hold, completed, handed_over. |
| Stage | id, tenant_id, project_id, template_id, name, sequence, status, criteria (JSONB), evidence_required (JSONB), certified_by, certified_at, conditions (JSONB) | belongs_to project, has_many inspections, evidence_documents | `status`: not_started, in_progress, evidence_submitted, under_review, certified, rejected. |
| Inspection | id, tenant_id, project_id, stage_id, inspector_id, scheduled_date, completed_date, outcome, findings (JSONB), photos (JSONB), report_document_id | belongs_to project, stage, inspector (user) | `outcome`: pass, conditional_pass, fail, re_inspection. |
| Milestone | id, tenant_id, project_id, name, planned_date, actual_date, status, evidence_id, owner_id | belongs_to project | `status`: pending, achieved, missed, re_baselined. Missed milestones trigger notification. |
| Contractor | id, tenant_id, registration_number, name, specialisations[], insurance_expiry, prequalification_status, performance_score | has_many projects | Prequalification: pending, approved, suspended, revoked. |

**Deployment Dependencies**
- Runtime: Laravel 11+ (PHP 8.3+) or Go 1.22+ (Laravel for workflow/logic, Go for photo serving).
- Database: PostgreSQL 15+ with JSONB and enum support.
- Object store: S3-compatible. Prefix: `/{tenant_id}/cms/{project_id}/`.
- Image processing: thumbnail generation service (300px, EXIF extraction).
- External: BDCE API, SPINE API, notification service.

### 25.5 Citi Utility Manager — Utility Billing and Service Integration

Handles property-linked accounts, meter readings, utility billing, payment capture, receipt generation, and service requests. Most financially sensitive module.

**API Endpoints**

| Method | Path | Purpose | Auth |
|---|---|---|---|
| GET | `/api/utility/accounts` | List utility accounts with balance, status, service type | authenticated |
| GET | `/api/utility/accounts/{id}` | Account detail with meter, invoices, payments, agreement | authenticated |
| POST | `/api/utility/accounts` | Create new utility account for a property/unit | officer, admin |
| GET | `/api/utility/invoices` | List invoices, filter by account, status, period, type | authenticated |
| GET | `/api/utility/invoices/{id}` | Invoice detail with line items, charges, credits, PDF link | authenticated |
| POST | `/api/utility/invoices` | Generate invoice (manual or scheduled) | officer, admin |
| POST | `/api/utility/invoices/{id}/pay` | Process payment (requires Idempotency-Key) | authenticated |
| GET | `/api/utility/payments` | List payments with method, status, reconciliation state | authenticated |
| GET | `/api/utility/payments/{id}/receipt` | Download receipt PDF | authenticated |
| POST | `/api/utility/payments/reconcile` | Manual payment reconciliation | officer, admin |
| GET | `/api/utility/meters` | List meters with type, unit, last reading, status | authenticated |
| POST | `/api/utility/meters/{id}/readings` | Submit meter reading | officer, inspector |
| GET | `/api/utility/service-requests` | List service requests | authenticated |
| POST | `/api/utility/service-requests` | Create service request | authenticated |
| PATCH | `/api/utility/service-requests/{id}/status` | Update request status | officer, admin |
| GET | `/api/utility/analytics/summary` | Module dashboard summary | authenticated |

**Pre-Integration Checklist**
- Payment gateway integration: Paystack, Flutterwave, or Interswitch with card, bank transfer, USSD. Webhook at `POST /api/utility/webhooks/payment`.
- Payment idempotency: every pay endpoint requires `Idempotency-Key`. Duplicates return original response. Keys stored 24h.
- Receipt generation: PDF with receipt number, account reference, amount, method, date, reconciliation code. Stored in object store.
- Invoice lifecycle: draft → issued → due → overdue → paid → void. Scheduled generation (monthly/quarterly/on-demand). Late fees per jurisdiction.
- Meter reading workflow: officer on-site, inspector, or smart meter API. Each reading stores value, timestamp, photo, GPS, reader ID.
- Reconciliation engine: gateway payments matched to open invoices. Manual payments require officer reconciliation. Unmatched held in suspense.
- Service request workflow: type (new_connection, disconnection, fault_report, meter_reading, account_enquiry), priority (low/medium/high/critical), status (submitted → assigned → in_progress → resolved → closed), SLA by priority.
- Integration with SPINE: accounts linked to parcels via parcel_id. New connections trigger SPINE layer updates.
- Integration with CMS: handoff creates initial utility accounts. Utility connection status is handoff checklist item.
- Financial reporting: daily settlement, monthly revenue, ageing analysis, reconciliation report (CSV + PDF).

**Data Model Requirements**

| Entity | Required fields | Relationships | Notes |
|---|---|---|---|
| Account | id, tenant_id, account_number, property_id, parcel_id, service_type, status, balance, owner_id, manager_id, created_at | belongs_to parcel (SPINE), has_many invoices, meters, service_requests | `service_type`: water, electricity, gas, waste, combined. `status`: active, suspended, closed, pending_connection. |
| Invoice | id, tenant_id, account_id, invoice_number, type, period_start, period_end, issued_date, due_date, line_items (JSONB), subtotal, tax, total, amount_paid, balance, status, void_reason | belongs_to account, has_many payments | `type`: monthly_charge, quarterly_bill, connection_fee, late_fee, adjustment. Status: draft, issued, due, overdue, paid, void, partially_paid. |
| Payment | id, tenant_id, invoice_id, account_id, amount, method, reference, gateway_response (JSONB), reconciliation_status, receipt_id, paid_by, paid_at, idempotency_key | belongs_to invoice, account | `method`: card, bank_transfer, ussd, cash, cheque, auto_debit. Reconciliation: matched, unmatched, pending. |
| Meter | id, tenant_id, account_id, meter_number, type, unit, installation_date, last_reading_value, last_reading_date, status | belongs_to account, has_many readings | `type`: water, electricity, gas. Status: active, faulty, replaced, decommissioned. |
| Meter Reading | id, tenant_id, meter_id, value, reading_date, photo_url, gps_coordinates, reader_id, source, created_at | belongs_to meter | `source`: manual_officer, manual_inspector, smart_meter_api, customer_submitted. |
| Service Request | id, tenant_id, account_id, type, priority, status, description, assigned_team, assigned_to, resolution_notes, created_at, resolved_at, sla_due_at | belongs_to account | Priority determines SLA. Critical: 2h response, 24h resolution. Low: 48h response, 14d resolution. |

**Deployment Dependencies**
- Runtime: Laravel 11+ (PHP 8.3+) or Go 1.22+ (Laravel for financial workflow, Go for high-throughput payment processing).
- Database: PostgreSQL 15+ with JSONB, Numeric(12,2) for monetary fields. Unique constraint on `idempotency_key`.
- Cache: Redis 7+ (idempotency keys 24h TTL, invoice cache 5min, rate limiter 10 payments/min per account).
- Queue: Redis Streams or RabbitMQ (invoice generation, receipt PDF, settlement reports, overdue reminders).
- Object store: S3-compatible. Prefix: `/{tenant_id}/utility/{account_id}/`.
- External: Payment gateway webhook, SMS gateway, email service, SPINE API, CMS API.

### Cross-Module Integration Matrix

| Integration | Source | Target | Data | Mechanism |
|---|---|---|---|---|
| Parcel context | SPINE | BDCE, CMS, Utility | parcel geometry, zone, status, owner, baseline | REST read — `GET /api/spine/parcels/{id}` |
| Permit to project | BDCE | CMS | approved permit, conditions, model ref, parcel link | Event — `permit.approved` → CMS creates project |
| Construction zone | CMS | SPINE | project boundary, stage status, active zone geometry | REST write — `POST /api/spine/layers` |
| Handoff to utility | CMS | Utility | completed project, parcel, property details, owner | Event — `project.handed_over` → Utility creates account |
| Payment status | Utility | Core | payment state, outstanding balance, SLA breach alerts | Event — `payment.received`, `invoice.overdue` |
| Rule result spatial | BDCE | SPINE | conflict geometry from rule evaluation | REST write — `POST /api/spine/conflicts` |
| User context | Core | All modules | user identity, roles, module access, tenant context | JWT claims + injected headers |
| Notification | Core | All modules | action required, status change, SLA warning | SSE stream + event bus |
| Audit | All modules | Core | state-changing operations | Event bus → Core consumer |

### Module Dependency Graph

- **Layer 0 — Core**: No module dependencies. Provides identity, tenant, audit, notification. Deployed first and must remain available for all operations.
- **Layer 1 — SPINE**: Depends on Core. Spatial context reference for all downstream modules.
- **Layer 2 — BDCE**: Depends on Core and SPINE. Approved permits flow to CMS. Rule results may create SPINE conflicts.
- **Layer 3 — CMS**: Depends on Core, SPINE, BDCE. Completed projects trigger Utility handoff. Construction layers published to SPINE.
- **Layer 4 — Citi Utility Manager**: Depends on Core, SPINE, CMS. Accounts created from CMS handoff. Payment events consumed by Core dashboard.

### Integration Testing Requirements

- Every module must pass integration tests against a real PostgreSQL instance (not mocked). Tests run in a transaction that is rolled back after each test.
- Health endpoint test: verify `GET /api/{module}/health` returns `200` with all dependencies healthy. Test degraded response with each dependency unavailable.
- Idempotency test: same `POST` request twice with same `Idempotency-Key`. First returns `201`, second returns `200` with `Idempotent-Replayed: true` and identical body.
- Authentication test: no JWT returns `401`. Insufficient role returns `403`. Expired token returns `401` with `token_expired` error code.
- Pagination contract test: default page 1 with 20 results. `total` and `filtered_total` always correct. `per_page` above 100 clamped to 100.
- Error format test: every endpoint returns errors in standard `{ error, detail, errors? }` format. HTTP status codes match error contract.
- SSE event test: SSE stream connects with valid JWT. Events received as JSON-encoded SSE messages. Reconnection resumes from last event ID.
- File upload test: valid file returns `{ file_id, name, size, type, url }`. Invalid type returns `422`. File > 50MB returns `413`.
- Cross-module integration test: create parcel in SPINE → create BDCE application → create CMS project from approved permit → verify project reads correct parcel data.
- Performance test: list endpoint with 10,000 records responds in under 500ms (p95). Upload handles 10 concurrent 10MB uploads. Tile serves 100 req/s with < 200ms.
- Rollback test: deploy migration, run it, run rollback, verify schema returns to pre-migration state with no data loss.
