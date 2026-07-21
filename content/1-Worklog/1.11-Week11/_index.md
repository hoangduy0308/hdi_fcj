---
title: "Week 11 Worklog"
date: 2026-07-05
weight: 11
chapter: false
pre: " <b> 1.11. </b> "
---
### Week 11 Objectives:

* Complete JWT, login, and user-profile tests.
* Build GPS proximity verification and review TrustBite CI.

### Tasks to be carried out this week:
| Day | Task | Start Date | Completion Date | Reference Material |
| --- | ---- | ---------- | --------------- | ------------------ |
| 2 | - Studied CognitoIdentityProvider JWT validation.<br>- Wrote tests for valid, expired, and truncated tokens. | 07/06/2026 | 07/06/2026 | [Cognito JWT Verification](https://docs.aws.amazon.com/cognito/)<br>[JWT Test Suite](https://github.com/trustbite-team-tcc/trustbite-review-system) |
| 3 | - Tested incorrect issuer, `client_id`, and signature cases.<br>- Refactored the in-memory RSA JWT helper. | 07/07/2026 | 07/07/2026 | [RSA JWT Helper](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Vitest Documentation](https://vitest.dev/) |
| 4 | - Wrote login and user-profile integration tests.<br>- Tested valid, SUSPENDED, and tokenless users. | 07/08/2026 | 07/08/2026 | [Authentication API](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Integration Test Guide](https://github.com/NguyenSonnt04/docs_trustbite) |
| 5 | - Built `gpsProximityService.js` with Haversine distance.<br>- Created `antiFraud.js` with validation and a configurable 200-meter threshold. | 07/09/2026 | 07/09/2026 | [GPS Proximity Service](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[Anti-Fraud Configuration](https://github.com/NguyenSonnt04/docs_trustbite) |
| 6 | - Added 13 GPS tests; all 80 tests passed.<br>- Reviewed GitHub Actions database migrations and Vitest. | 07/10/2026 | 07/10/2026 | [GPS Test Suite](https://github.com/trustbite-team-tcc/trustbite-review-system)<br>[GitHub Actions](https://docs.github.com/actions) |

### Week 11 Achievements:

* Completed Cognito JWT, login, and user-profile tests.
* Built a configurable, validated GPS Proximity Service; all 80 tests passed.
