# Requirements Ledger

| ID | Requirement | Type | Verification | Status |
|---|---|---|---|---|
| M01 | Load and validate requirements JSON | MUST | schema tests + judge path | Not started |
| M02 | Sort requirements by numeric `order` | RULE | unit test | Not started |
| M03 | Upload multiple PDFs, page count, removal | MUST | integration test | Not started |
| M04 | Reject non-PDF, damaged, and encrypted files safely | MUST/BONUS | integration test | Not started |
| M05 | Enforce one-file/one-requirement matching | RULE | unit test | Not started |
| M06 | Capture expiry dates for applicable matches | MUST | unit test + judge path | Not started |
| M07 | Compute exact five statuses immediately | STRING/RULE | unit tests S01-S06 | Not started |
| M08 | Detect byte-identical duplicates | MUST | unit test S07 | Not started |
| M09 | Disable Generate and explain every blocker | UX | judge path | Not started |
| M10 | Generate English cover with all required fields | MUST | PDF structure test | Not started |
| M11 | Merge all pages in requirement order | RULE | PDF structure test | Not started |
| M12 | Add readable non-overlapping footer to every page | MUST | render + structure test | Not started |
| M13 | Download `<tender_id>_Package.pdf` | STRING | integration test | Not started |
| M14 | Complete Bangla/English UI | MUST/UX | language audit | Not started |
| L01 | Maximum 30 files and 50 MB total | LIMIT | boundary tests | Not started |
| D01 | Correct sample output under `output/` | DELIVERABLE | open/render/inspect | Not started |
| D02 | Status screenshot under `screenshots/` | DELIVERABLE | visual inspection | Not started |
| D03 | README and MIT license | DELIVERABLE | repository audit | Not started |
| D04 | Public HTTPS deployment matching final commit | DELIVERABLE | incognito judge path | Blocked: remote missing |
| B01 | Filename auto-match suggestions | BONUS | unit + judge path | Not started |
| B02 | Index page | BONUS | PDF structure test | Not started |
| B03 | CSV checklist export | BONUS | content test | Not started |
| B04 | Save and reopen work | BONUS | reload test | Not started |
