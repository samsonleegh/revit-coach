# Revit troubleshooting playbook

Diagnostic orders for the most common "stuck" situations. Check causes roughly in the order listed — cheapest and most likely first. Paths can differ slightly between versions; confirm against Autodesk Help if unsure.

## 1. "I can't see an element in this view"
1. **Temporary Hide/Isolate** — the view has a cyan border and "Temporary Hide/Isolate" label. Reset: View Control Bar › sunglasses icon › Reset Temporary Hide/Isolate (HR).
2. **Hidden in view** — turn on Reveal Hidden Elements (lightbulb on the View Control Bar; hidden items show in magenta). Select it › right-click › Unhide in View › Elements or Category.
3. **Visibility/Graphics** (VG / VV) — category or subcategory unticked; a **filter** hiding it (Filters tab); links (Revit Links tab); CAD (Imported Categories tab).
4. **View template** — if VG settings are greyed out, a view template controls them. Properties › Identity Data › View Template. Changing the template affects every view using it ⚠️.
5. **View Range** (plans/RCPs) — Properties › Extents › View Range › Edit. Element may be above Top / Cut Plane or below View Depth. Also check for a **Plan Region** overriding the range.
6. **Crop / clipping** — crop region, annotation crop, Far Clipping (sections/elevations), or a **Scope Box** limiting extents.
7. **Phases** — view's Phase and Phase Filter vs the element's Phase Created / Phase Demolished.
8. **Design Options** — element is in a secondary option; check VG › Design Options tab or the Design Options status-bar control.
9. **Worksets** — workset hidden in this view (VG › Worksets tab) or **closed** (Collaborate › Manage Collaboration › Worksets › "Opened" = No).
10. **Detail Level / family visibility** — family geometry set to show only at Coarse/Medium/Fine, or controlled by a visibility parameter in the family.
11. **Discipline / Underlay** — view Discipline (e.g. Structural) or Underlay settings.
12. **Wrong level / offset** — element hosted to a different level or with a large base/top offset.

## 2. "I can't select or move an element"
1. **Selection toggles** at the bottom-right of the status bar: Select Links, Select Underlay Elements, Select Pinned Elements, Select Elements by Face, Drag Elements on Selection.
2. **Pinned** — unpin with UP (pin with PN). Pinned items may not be selectable if Select Pinned Elements is off.
3. **In a group** — press Tab to cycle to the element, or select the group › Edit Group.
4. **In a linked model** — it belongs to another file; edit it there.
5. **Overlapping elements** — hover and press Tab to cycle, watch the status bar for which element is highlighted.
6. **Owned by someone else** (workshared) — you can select but not edit. Use Place Request, or ask them to Synchronize and relinquish.

## 3. Worksharing basics
- Always work in a **local copy**, never directly in the central: open the central with "Create New Local" ticked.
- **Synchronize with Central**: Collaborate › Synchronize › Synchronize with Central. Do it often, and before leaving.
- **Reload Latest** to pull others' changes without sending yours.
- **Relinquish All Mine** releases elements you borrowed without syncing changes.
- "Element is owned by another user" → editing request, or they sync and relinquish.
- To test something risky: open with **Detach from Central** ⚠️ and save under a new name — never Save As over the central.

## 4. Rooms and areas
- "Room is not in a properly enclosed region" — gap in bounding walls; use Room Separator lines (Architecture › Room & Area › Room Separator) to close gaps.
- Walls in a **linked model** not bounding rooms — select link › Edit Type › tick **Room Bounding**.
- Room height / volume wrong — room Upper Limit and Limit Offset in Properties; volume calculation in Architecture › Room & Area panel dropdown › Area and Volume Computations.
- Duplicate room numbers — warning only; fix numbers to avoid schedule/tag issues.

## 5. Views and sheets
- A model view can be on **only one sheet**. To show it again: right-click the view › Duplicate View › Duplicate with Detailing or Duplicate as Dependent. (Schedules and legends can go on multiple sheets.)
- Title / viewport style — select viewport › Properties › Type Selector.
- Aligning views across sheets — Guide Grid (View › Sheet Composition › Guide Grid).
- Annotation size wrong — check view Scale; annotations are sized for print.

## 6. Schedules
- Field missing — wrong schedule category, or the parameter is a project parameter not shared/assigned to that category. Shared parameters are needed to tag and schedule the same custom field.
- Showing totals instead of rows — untick/tick "Itemize every instance" (Sorting/Grouping tab).
- Calculations — Fields tab › Calculated Value (formula or percentage).
- Editing a schedule cell edits the model element's parameter ⚠️ (type parameters change all instances of that type).

## 7. Families
- Edit a family: select instance › Edit Family; Load into Project when done (choose whether to overwrite parameter values).
- Changing a **type parameter** changes all instances of that type; duplicate the type first (Edit Type › Duplicate) if you only want some changed.
- Family won't cut the wall/host — check it's hosted, or use Modify › Cut for void-based families.
- Wrong category (e.g. not appearing in a schedule) — in Family Editor: Create › Properties › Family Category and Parameters.

## 8. Common warnings
- Review all: Manage › Inquiry › Warnings. A large warning count slows models.
- "Highlighted walls overlap" — duplicate or overlapping walls; delete or adjust one.
- "Line is too short" — Revit can't draw very short lines (~0.8 mm); redraw longer or snap differently.
- "Can't keep elements joined" — joined geometry conflicts; unjoin (Modify › Geometry › Join › Unjoin Geometry) and rejoin.
- "Identical instances in the same place" — duplicates, often from copy/paste; delete the duplicate.

## 9. Slow model
- Imported CAD → link instead of import, and only into views that need it.
- Many warnings → clean up.
- Unused families/types → Purge Unused ⚠️ (coordinate with the team; don't purge in a template-controlled project without asking).
- Large central file → "Compact" when syncing or saving (ask the BIM manager first).
- Close unused views (View › Windows › Close Inactive Views).

## 10. Exporting
- PDF: File › Export › PDF (native since Revit 2022), or Print with a PDF printer on older versions.
- DWG: File › Export › CAD Formats › DWG — use the firm's export setup if one exists.
- IFC: File › Export › IFC — for CORENET X use the IFC-SG setup (see singapore-bim-context.md).

## Common default shortcuts
(Firms can customise these — check View › User Interface › Keyboard Shortcuts, or KS.)
| Shortcut | Command |
|---|---|
| VG / VV | Visibility/Graphics |
| HH / HI / HR | Temporary hide / isolate / reset |
| EH / VH | Hide element / category in view (permanent) |
| WA / DR / WN | Wall / Door / Window |
| RM / RT | Room / Tag room |
| DI | Aligned dimension |
| AL | Align |
| TR | Trim/Extend to corner |
| SL | Split element |
| MV / CO / RO | Move / Copy / Rotate |
| MM / DM | Mirror – pick axis / draw axis |
| PN / UP | Pin / Unpin |
| CS | Create similar |
| MA | Match type properties |
| RP | Reference plane |
| TL | Thin lines |
| ZF / ZA | Zoom to fit / zoom all windows to fit |
| WT | Tile windows |
| KS | Keyboard shortcuts |
