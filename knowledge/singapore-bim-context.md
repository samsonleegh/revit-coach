# Singapore BIM submission context

Last checked: October 2026. Rules change — always verify the current requirement on official sources (URA circulars, BCA, CORENET X site) before relying on this.

## CORENET X
- Singapore's integrated digital regulatory submission platform. Instead of submitting separately to each agency (URA, BCA, SCDF, LTA, NEA, NParks, PUB, SLA and others), a project makes coordinated submissions at key gateways: Design Gateway, Construction Gateway and Completion Gateway (plus a Piling Gateway where applicable).
- **Mandate (per URA circular DC26-08, "Updates to CORENET X Implementation Plan"):**
  - From October 2025: mandatory for new projects with GFA ≥ 30,000 m².
  - From 1 October 2026: mandatory for all new projects with GFA ≥ 5,000 m².
  - Check the circular for details on ongoing projects, smaller projects and transition rules.
  - Source: https://www.ura.gov.sg/guidelines/circulars/dc26-08/

## IFC-SG (IFC+SG)
- Singapore's localised IFC standard for BIM submissions under CORENET X. Models are authored in Revit as normal, then exported to IFC with Singapore-specific classifications and parameters.
- BIM submissions in IFC+SG format are required for qualifying new erections / major additions — confirm against the current circular for the project.
- Typical Revit-side tasks:
  1. Load the official IFC-SG **shared parameters** and set up the firm's template accordingly (usually a BIM manager task ⚠️ — project-wide change).
  2. Make sure elements are modelled with the right **Revit category** and mapped to the correct IFC class (e.g. via IFC export mapping or the "Export to IFC As" parameter).
  3. Fill the required IFC-SG parameters on each element type/instance (schedules are the fastest way to check and fill these in bulk).
  4. Export with **File › Export › IFC** using the IFC-SG export setup/mapping from the official resource kit.
  5. Check the exported IFC with the official checking tools before submission.
- Official resources (IFC-SG resource kit, industry mapping, Code of Practice for CORENET X submissions) are published by the agencies — upload the versions your firm uses into this project for accurate, specific answers.

## How to use this file
- For "how do I do X in Revit for IFC-SG" — answer the Revit steps, and point to the specific official document if it's in project knowledge.
- For "is this compliant / what does the code require" — out of scope for this coach; verify against the actual code (SCDF Fire Code, BCA Approved Document, URA guidelines, etc.).
