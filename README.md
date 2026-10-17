# Revit Coach — setup guide

A Claude Project on claude.ai that acts as a Revit coach. About 10 minutes to set up.

## What's in this folder
| File | Where it goes |
|---|---|
| `instructions.md` | Paste into the project's **Instructions** |
| `knowledge/my-setup.md` | Fill in, then upload to project **Files** |
| `knowledge/revit-troubleshooting-playbook.md` | Upload to project **Files** |
| `knowledge/singapore-bim-context.md` | Upload to project **Files** |

## Setup
1. **Fill in `knowledge/my-setup.md`** — at least the Revit version and what you get stuck on. Blanks are fine.
2. Go to **claude.ai** (or the Claude desktop app) › **Projects** › **Create project**. Name it "Revit Coach".
3. **Instructions**: open the project's instructions box and paste the full contents of `instructions.md`.
4. **Files**: upload the three files in `knowledge/`. Also upload, if you have them:
   - the firm's BIM manual / Revit standards / template guide (PDF)
   - the IFC-SG / CORENET X guides your firm uses
5. In a chat inside the project, turn on **Web search** (tools menu next to the message box) so it can check Autodesk Help for your exact version.

A paid plan (Pro) is recommended for regular use — higher limits and better handling of large knowledge files.

## Using it
- **Screenshot straight into chat**: press `Win + Shift + S`, select the area, then `Ctrl + V` in the Claude message box.
- Good screenshots show the whole Revit window (view, Properties palette, any warning). Crop out anything you don't want shared.
- Say what you were trying to do, not just what went wrong: "I want the furniture to show in this plan but it's gone" beats "furniture missing".
- **One problem per chat.** Start a new chat for a new problem so old context doesn't confuse it.

## Make it smarter over time
When a problem is solved, ask: *"Summarise this fix in 3 lines for my log."* Paste the answer into a `solved-log.md` file and re-upload it to the project every so often. The coach will then know your past fixes and your firm's quirks.

Update `my-setup.md` when you change Revit version or project.
