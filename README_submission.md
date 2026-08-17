# Lab 17 - README_submission

Pham Thanh Long - 2A202601259. `src/memory_student.py`: 4/4 TODO. **11/11 PASS, hit rate 100%** (`reports/benchmark.json`); no-memory 2/11 = 18.2%. Golden **20/20** (`reports/golden_benchmark.json`).

## 3 cau bat buoc

**1. Layer quan trong nhat: long-term.** Bon case phu thuoc truc tiep - E02 (`Python`), E03 (`benchmark report`, `16:00`), E08 (`BLUEBIRD-42`/`TypeScript`/`NestJS`), E09 (`LOTUS-88`, chan leak `ORCHID-27`) = 20/56 diem; E07 cung lay `Python` tu day. Chi layer nay bat buoc cross-session recall.

**2. Context Block (Zep) vs Redis + Qdrant.** Zep tra ve context block tong hop san + fact co validity range, khong phai tu viet extraction/ranking; doi lai la latency va mat kiem soat kich thuoc (E08 114.4s; block tho 1557 token phai cat con 324 o E07). Redis + Qdrant nhanh, deterministic, tu chu schema, nhung phai tu build extraction, conflict resolution va temporal validity - dung phan lam nen E08.

**3. Guardrail chong memory poisoning.** Gate ghi bang `privacy_guard.can_write_type` + `data/consent.json` (opt-in truoc durable ingestion), redact PII truoc ingest, va scope moi call long-term/episodic theo `user_id` - E09 chung minh query cua Lan khong keo `ORCHID-27` cua Minh vao. Them: chi tin fact co provenance, uu tien fact moi khi conflict, khong ingest lai text model tu sinh.

## 4 cau phan tich

1. **Hit rate thap nhat:** run student khong co layer nao thap, ca 5 layer 100%. Baseline no-memory: short_term 100% (2/2), long_term/episodic/semantic/mixed 0%. Diem yeu con lai la chi phi, khong phai do chinh xac (E04 29.5s).
2. **Nhieu token nhat:** E03 1575 token, roi E02 1566 va E08 1000; long-term ton nhat vi context block gom summary + episodes + fact search.
3. **E07 (mixed)** = long-term + semantic. `budget_breakdown`: long_term 1557 -> 324 token (limit 320), semantic 148/240, short_term va episodic 0. Evidence bat buoc: `Python` (long-term) va `Idempotency-Key` (semantic); thieu mot la FAIL.
4. **Token reduction** 14.2% (memory) vs 81.8% (no-memory), nhung hit rate 100% vs 18.2%. No-memory retrieve 0 token o 9 case nen reduction = 1.0; khong retrieve gi thi luon "re" nhat. Chi doc reduction cung hit rate.

## E08 recency, E10 compaction

E08 dung `scope="edges", limit=20` de lay fact kem validity range: stack BLUEBIRD-42 doi sang TypeScript/NestJS o stage sau, `limit` thap tra ve fact cu va FAIL. E10: sliding compaction giu `REVIEW-DEADLINE-1600`/`Friday`/`16:00` trong `<DURABLE_NOTES>` du raw turn bi evict; buffer thuan khong du: token tang tuyen tinh, vuot pressure la constraint bi cat cung filler.

## Bang chung

`submission/long_term.png` (E02/E03/E08), `episodic.png` (E04/E05), `semantic.png` (E06/E11), `privacy.png` (forget + `--verify-only`). Bonus UI: `src/demo_ui.py` (`make ui`) + `submission/ui.png`.
