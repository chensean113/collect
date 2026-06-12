# Work Allocation Report — [Team ID]

> **Instructions:** Complete this document as a team before or alongside your final submission.
> Submit one copy per team via EEClass. This document is shared with all markers.
> Be specific — vague entries ("we all helped") will prevent individual contribution adjustments from being applied in your favour.

---

## 1. Team Members

| Full Name | Student ID | GitHub Username | Email |
|-----------|-----------|----------------|-------|
|陳昱翔|113403516|chensean113|sean20060530@gmail.com|
|黃士桓|113403026|shihuan-haha|shihuan.h04@gmail.com|
|林于翔|113403540|iceeeeeeeeas|fkualldayallnight@gmail.com|

---

## 2. Task Ownership

For each task, name the **primary owner** (the person most responsible for delivering it)
and any **supporting members** (who assisted but were not the lead). Leave the Notes column
for anything that deviates from the standard expectation (e.g., task was pair-programmed,
or reassigned mid-project).

### Code Repository

| Task | Primary Owner | Supporting Member(s) | Notes |
|------|--------------|---------------------|-------|
| **Task 1** — Relational schema design (`schema.sql`) |陳昱翔| | Designed all tables, keys, and constraints. |
| **Task 2a** — Core availability & fare queries (`query_national_rail_availability`, `query_metro_schedules`, `query_national_rail_fare`, `query_metro_fare`) |黃士桓| |Implemented baseline SQL queries.|
| **Task 2b** — Seat & user queries (`query_available_seats`, `query_user_profile`, `query_user_bookings`, `query_payment_info`) |黃士桓| |Implemented baseline lookup SQL queries.|
| **Task 2c** — Write operations (`execute_booking`, `execute_cancellation`) |陳昱翔| |Handled atomic database transactions and rollback logic.|
| **Task 2d** — Authentication queries (`login_user`, `register_user`, `get_user_secret_question`, `verify_secret_answer`, `update_password`) |陳昱翔| | |
| **Task 3** — PostgreSQL seeding (`seed_postgres.py`) |陳昱翔| |Implemented both PostgreSQL and Vector DB (pgvector) seeding scripts.|
| **Task 4** — Neo4j graph design & seeding (`seed_neo4j.py`, `seed.cypher`) |林于翔| |Designed graph topology and authored Cypher seed scripts. |
| **Task 5** — Neo4j query functions (`graph/queries.py`) |黃士桓|陳昱翔|黃士桓 handled baseline queries; 陳昱翔 implemented APOC Dijkstra fastest/cheapest routing and added Neo4j fare properties.|
| **Task 6** *(if attempted)* — Optional extension | | | |

### Design Document

| Section | Primary Author | Supporting Member(s) | Notes |
|---------|--------------|---------------------|-------|
| Section 1 — ER Diagram |黃士桓| | |
| Section 2 — Normalisation Justification |黃士桓|陳昱翔| |
| Section 3 — Graph Database Design Rationale |陳昱翔|黃士桓| |
| Section 4 — Vector / RAG Design |黃士桓| | |
| Section 5 — AI Tool Usage Evidence |陳昱翔| | |
| Section 6 — Reflection & Trade-offs |黃士桓| | |
| Section 7 — Optional Extension *(if applicable)* | | | |

---

## 3. Estimated Contribution Percentages

Based on the task allocation above, what percentage of total team effort do you estimate each member contributed?
All members must sum to 100%.

| Member | Estimated % | Brief justification |
|--------|-----------|---------------------|
|陳昱翔| 45% |Handled Schema, Data Seeding, Vector DB, Advanced Algorithms (bcrypt/Dijkstra), Agent Tool Integration|
|黃士桓| 35% |Implementing the baseline queries across BOTH relational and graph database files.|
|林于翔| 20% |Handled the Neo4j Graph Schema design and `seed_neo4j.py|
| **Total** | **100%** | |

---

## 4. Mid-Project Changes

If any tasks were reassigned or the original plan changed significantly, document it here.
If nothing changed, write "No changes."

| Change | Original plan | Revised plan | Reason |
|--------|--------------|-------------|--------|
|No changes| | | |

---

## 5. Team Declaration

We confirm that this work allocation accurately reflects how responsibilities were divided within our team.

| Name | Signature / Typed name | Date |
|------|----------------------|------|
|陳昱翔|陳昱翔|06-12|
|黃士桓|黃士桓|06-12|
|林于翔|林于翔|06-12|
