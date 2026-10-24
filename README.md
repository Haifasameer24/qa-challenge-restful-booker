# QA Challenge: Restful Booker Platform (Shady Meadows B&B)

Manual quality assessment of a hotel booking web application, with a release recommendation.

- **Application tested:** https://automationintesting.online/
- **Source code of the application:** https://github.com/mwinteringham/restful-booker-platform
- **Tester:** Haifa Samir
- **Test period:** 20-10-2026 to 24-10-2026
  

## Scope

All testing was manual and performed through the user interface: room browsing, availability search, booking, the contact form, the admin area, and navigation.

**Excluded by decision of the tester:** API testing and test automation. Performance, penetration and cross-browser testing were also out of scope. See the Test Strategy for the full scope.

## Repository Contents

| Folder | Content |
|---|---|
| `strategy/` | Test Strategy: scope, assumptions, risks, priorities, environment, exit criteria |
| `test-cases/` | `Test_Cases_Execution.xlsx`: 60 test cases with steps, test data, expected and actual results, status and evidence |
| `bugs/` | Bug report (13 bugs, 6 enhancements) and the `evidence/` folder with screenshots |
| `api/` | Note explaining that API testing was out of scope |
| `final-report/` | Final QA report with the release recommendation |

## Results Summary

| Status | Count |
|---|---|
| PASS | [39] |
| FAIL | [19] |
| BLOCKED | [2] |
| NOT RUN | [0] |
| **Total** | **[60]** |

Update these numbers from the Summary sheet of the spreadsheet before submitting.

## Release Recommendation

**NO-GO.**

The normal booking path works, but date handling in the booking flow fails: reversed and past dates are accepted, a negative total is shown, and overlapping bookings are recorded as accepted. Guest data exposure reported by the automated security runs must be confirmed manually, and if confirmed it is a Critical defect. Details and conditions to change the decision are in `final-report/`.

## How to Read the Evidence

- Each test case in the spreadsheet has a **Status** (PASS, FAIL, BLOCKED, NOT RUN) and an **Evidence** column.
- Screenshots in `bugs/evidence/` are named after the test case, for example `TC-016_reversed_dates.png`.
- Bug IDs (BUG-01 to BUG-13) in the bug report reference the related test cases.

## Known Limitations

- The application is a **shared public demo** that resets its bookings and messages every few minutes, so results reflect the test period only and booking persistence was not proven on a private copy.
- **API behaviour was not tested**, so service-level defects (validation, authorization, status codes) may exist undetected.
- No automated regression tests were built; re-testing after fixes must be repeated manually.
- Not assessed: performance, accessibility, wider browser coverage, room amenities and the "Accessible" flag.
- Some findings come from automated runs of a testing platform dated 22 October 2026 and were not all reproduced manually; these are marked as pending confirmation in the final report.
