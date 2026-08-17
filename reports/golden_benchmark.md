# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1236.3 ms**
- Average token reduction vs full source context: **6.3%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.5 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.1 | 133 | 0.0% |  |
| G08 | long_term | PASS | 3812.2 | 794 | 0.0% |  |
| G09 | long_term | PASS | 1519.1 | 1467 | 0.0% |  |
| G12 | semantic | PASS | 316.1 | 418 | 8.9% |  |
| G14 | semantic | PASS | 308.2 | 270 | 30.2% |  |
| G15 | semantic | PASS | 356.7 | 270 | 41.2% |  |
| G19 | mixed | PASS | 2535.0 | 581 | 0.0% |  |
| G03 | long_term | PASS | 1718.6 | 1456 | 0.0% |  |
| G04 | long_term | PASS | 1422.8 | 1463 | 0.0% |  |
| G05 | long_term | PASS | 1758.7 | 1452 | 0.0% |  |
| G10 | episodic | PASS | 324.4 | 582 | 0.0% |  |
| G11 | episodic | PASS | 380.4 | 614 | 0.0% |  |
| G13 | semantic | PASS | 303.5 | 416 | 26.4% |  |
| G16 | mixed | PASS | 1772.4 | 581 | 0.0% |  |
| G18 | mixed | PASS | 847.0 | 500 | 11.5% |  |
| G20 | mixed | PASS | 2166.1 | 831 | 0.0% |  |
| G06 | long_term | PASS | 1565.0 | 1453 | 0.0% |  |
| G07 | long_term | PASS | 1561.5 | 1455 | 0.0% |  |
| G17 | mixed | PASS | 2058.4 | 581 | 8.1% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G08 - long_term

`<USER_SUMMARY> Lan Tran's project is LOTUS-88, prioritizing Java and Spring Boot for backend development.  Lan Tran prefers Java and Spring Boot and avoids using Python in backend examples. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88`

### G09 - long_term

`<USER_SUMMARY> The user is learning about async/await and coroutines versus Tasks in programming. They have a deadline for an open loop LAB-REPORT-1600 by Friday at 16:00. The user is currently debugging async HTTP requests and has attempted to increase the timeout to 60 seconds without success. The user is investigating connection pool, client lifecycle, and concurrency. A more effective approach involves reusing the aiohttp ClientSession and setting concurrency to 20, resolving the issue of connection churn rather than timeout thresholds, related to ASYNC-FIX-20. The user noted that increasing the timeout was ineffective, but using ClientSession with a concurrency of 20 resolved the connec`

### G12 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} metadata= EPISODE: For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal `

### G14 - semantic

`EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. metadata= EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodi`

### G15 - semantic

`EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} metadata= EPISODE: Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL. metadata= EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodi`

### G19 - mixed

`<LONG_TERM> <USER_SUMMARY> Lan Tran's project is LOTUS-88, prioritizing Java and Spring Boot for backend development.  Lan Tran prefers Java and Spring Boot and avoids using Python in backend examples. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hi`

### G03 - long_term

`<USER_SUMMARY> The user is learning about async/await and coroutines versus Tasks in programming. They have a deadline for an open loop LAB-REPORT-1600 by Friday at 16:00. The user is currently debugging async HTTP requests and has attempted to increase the timeout to 60 seconds without success. The user is investigating connection pool, client lifecycle, and concurrency. A more effective approach involves reusing the aiohttp ClientSession and setting concurrency to 20, resolving the issue of connection churn rather than timeout thresholds, related to ASYNC-FIX-20. The user noted that increasing the timeout was ineffective, but using ClientSession with a concurrency of 20 resolved the connec`

### G04 - long_term

`<USER_SUMMARY> The user is learning about async/await and coroutines versus Tasks in programming. They have a deadline for an open loop LAB-REPORT-1600 by Friday at 16:00. The user is currently debugging async HTTP requests and has attempted to increase the timeout to 60 seconds without success. The user is investigating connection pool, client lifecycle, and concurrency. A more effective approach involves reusing the aiohttp ClientSession and setting concurrency to 20, resolving the issue of connection churn rather than timeout thresholds, related to ASYNC-FIX-20. The user noted that increasing the timeout was ineffective, but using ClientSession with a concurrency of 20 resolved the connec`

### G05 - long_term

`<USER_SUMMARY> The user is learning about async/await and coroutines versus Tasks in programming. They have a deadline for an open loop LAB-REPORT-1600 by Friday at 16:00. The user is currently debugging async HTTP requests and has attempted to increase the timeout to 60 seconds without success. The user is investigating connection pool, client lifecycle, and concurrency. A more effective approach involves reusing the aiohttp ClientSession and setting concurrency to 20, resolving the issue of connection churn rather than timeout thresholds, related to ASYNC-FIX-20. The user noted that increasing the timeout was ineffective, but using ClientSession with a concurrency of 20 resolved the connec`

### G10 - episodic

`EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Toi se uu tien timeline khi giai thich coroutine va Task. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nh`

### G11 - episodic

`EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; ClientSession + concurrency=20 giai quyet connection churn. EPISODE: Cap nhat moi: voi du an cong ty BLUEB`

### G13 - semantic

`EPISODE: {"id":"kb-async-http","entity":"Async HTTP Incident Playbook","summary":"When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST.","source":"incident-playbook-2026","updated_at":"2026-08-11T00:00:00Z"} metadata= EPISODE: When async HTTP calls time out, inspect connection pooling, downstream saturation and concurrency before increasing timeout. Reuse a long-lived client session where possible. Marker: CONN-POOL-FIRST. metadata= EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data witho`

### G16 - mixed

`<LONG_TERM> <USER_SUMMARY> The user is learning about async/await and coroutines versus Tasks in programming. They have a deadline for an open loop LAB-REPORT-1600 by Friday at 16:00. The user is currently debugging async HTTP requests and has attempted to increase the timeout to 60 seconds without success. The user is investigating connection pool, client lifecycle, and concurrency. A more effective approach involves reusing the aiohttp ClientSession and setting concurrency to 20, resolving the issue of connection churn rather than timeout thresholds, related to ASYNC-FIX-20. The user noted that increasing the timeout was ineffective, but using ClientSession with a concurrency of 20 resolve`

### G18 - mixed

`<EPISODIC> EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: Toi se uu tien timeline khi giai thich coroutine va Task. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE`

### G20 - mixed

`<LONG_TERM> <USER_SUMMARY> The user is learning about async/await and coroutines versus Tasks in programming. They have a deadline for an open loop LAB-REPORT-1600 by Friday at 16:00. The user is currently debugging async HTTP requests and has attempted to increase the timeout to 60 seconds without success. The user is investigating connection pool, client lifecycle, and concurrency. A more effective approach involves reusing the aiohttp ClientSession and setting concurrency to 20, resolving the issue of connection churn rather than timeout thresholds, related to ASYNC-FIX-20. The user noted that increasing the timeout was ineffective, but using ClientSession with a concurrency of 20 resolve`

### G06 - long_term

`<USER_SUMMARY> The user is learning about async/await and coroutines versus Tasks in programming. They have a deadline for an open loop LAB-REPORT-1600 by Friday at 16:00. The user is currently debugging async HTTP requests and has attempted to increase the timeout to 60 seconds without success. The user is investigating connection pool, client lifecycle, and concurrency. A more effective approach involves reusing the aiohttp ClientSession and setting concurrency to 20, resolving the issue of connection churn rather than timeout thresholds, related to ASYNC-FIX-20. The user noted that increasing the timeout was ineffective, but using ClientSession with a concurrency of 20 resolved the connec`

### G07 - long_term

`<USER_SUMMARY> The user is learning about async/await and coroutines versus Tasks in programming. They have a deadline for an open loop LAB-REPORT-1600 by Friday at 16:00. The user is currently debugging async HTTP requests and has attempted to increase the timeout to 60 seconds without success. The user is investigating connection pool, client lifecycle, and concurrency. A more effective approach involves reusing the aiohttp ClientSession and setting concurrency to 20, resolving the issue of connection churn rather than timeout thresholds, related to ASYNC-FIX-20. The user noted that increasing the timeout was ineffective, but using ClientSession with a concurrency of 20 resolved the connec`

### G17 - mixed

`<LONG_TERM> <USER_SUMMARY> The user is learning about async/await and coroutines versus Tasks in programming. They have a deadline for an open loop LAB-REPORT-1600 by Friday at 16:00. The user is currently debugging async HTTP requests and has attempted to increase the timeout to 60 seconds without success. The user is investigating connection pool, client lifecycle, and concurrency. A more effective approach involves reusing the aiohttp ClientSession and setting concurrency to 20, resolving the issue of connection churn rather than timeout thresholds, related to ASYNC-FIX-20. The user noted that increasing the timeout was ineffective, but using ClientSession with a concurrency of 20 resolve`
