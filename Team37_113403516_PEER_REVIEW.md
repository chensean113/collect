# Peer Review Report

> **Instructions:** Complete this form **individually and independently**.
> Do not discuss your ratings with teammates before submitting.
> Submit via EEClass as a **separate, confidential submission** — not in the shared team repo.
> Your teammates will not see this report.
>
> Reference the team's `WORK_ALLOCATION_TEMPLATE.md` when completing this form.

---

## Your Details

| Field | Your answer |
|-------|------------|
| Full Name |陳昱翔|
| Student ID |113403516|
| Team ID |37|
| Date submitted |6/12|

---

## Rating Scale

| Rating | Meaning |
|--------|---------|
| **5** | Exceeded expectations — delivered more than agreed; helped teammates; consistently high quality |
| **4** | Met expectations fully — delivered exactly what was agreed; on time; good quality |
| **3** | Mostly met expectations — minor shortfalls; one or two items completed late or with help |
| **2** | Partially met expectations — noticeable gaps; teammates had to cover some tasks |
| **1** | Did not meet expectations — significant tasks left incomplete; very limited contribution |

---

## Section A — Self-Assessment

### A1. What did you personally implement?

List the specific tasks, functions, files, or document sections that you were the primary author of.
Be specific (e.g., "I designed all 12 tables in schema.sql and implemented query_national_rail_availability and execute_booking").

> *Your answer:* I was the primary author for the majority of the core database architecture and documentation. Specifically, I implemented:
1.Relational Schema Design: Designed all tables, constraints, and relationships in databases/relational/schema.sql, ensuring 3NF normalization.
2.PostgreSQL & Vector DB Seeding: Implemented all insertion logic in skeleton/seed_postgres.py (using ON CONFLICT DO NOTHING) and successfully seeded the RAG policy documents.
3.Relational Queries & Security: Co-authored several SQL functions in databases/relational/queries.py and personally implemented the bcrypt password hashing logic (import bcrypt) to meet the strict security requirements for user authentication.
4.Advanced Graph Queries & Schema: Implemented the APOC Dijkstra algorithm for the fastest (query_shortest_route) and cheapest (query_cheapest_route) route queries. To support the cheapest route logic, I also extended the Neo4j graph schema by adding fare properties to the relationships.
5.LLM Agent Integration: Acted as the integration lead by wiring up the newly created database queries into skeleton/agent.py. I registered the functions in the TOOLS list, updated TOOLS_SCHEMA, and mapped them in _execute_tool so the AI could call them correctly.
6.Integration & Bug Fixing: Acted as the final code reviewer, fixing critical bugs such as correcting Neo4j relationship names to match the grading rubric.
---

### A2. What challenges did you face?

Describe any technical or collaboration difficulties you personally encountered and how you resolved them.

> *Your answer:*A key challenge was integrating our completed database queries into the LLM pipeline (skeleton/agent.py). When registering complex tools like make_booking or find_route, the LLM would occasionally hallucinate parameter values or fail to pass required arguments like fare_class or seat_id. I resolved this by carefully debugging the LLM's JSON outputs, strictly refining the definitions in the TOOLS list and TOOLS_SCHEMA, and explicitly mapping the parameters in the _execute_tool function to ensure the Gradio UI could seamlessly trigger the correct database operations without crashing.

---

### A3. Self-rating

| Criterion | Rating (1–5) | Justification (1–2 sentences) |
|-----------|-------------|-------------------------------|
| I delivered the tasks assigned to me in the work allocation |5|I completed all my assigned tasks (Schema, Seeding ,Queries) and took on extra work to assist others.|
| The quality of my work was satisfactory |5|I ensured production-level quality, from bcrypt security implementation to APOC Dijkstra routing and flawless agent integration.|
| I communicated well and kept the team informed |5|I actively managed the AI_SESSION_CONTEXT.md and guided the team on schema dependencies.|
| I met deadlines agreed within the team |5|All my components were delivered early, giving me time to handle the final system integration.|
| **Overall self-rating** |5|I laid the foundation for the databases and successfully integrated both relational and graph queries into the final AI agent.|

---

### A4. Estimated contribution percentage

What percentage of the total team effort do you estimate you personally contributed?

> My estimated contribution: **50%**

---

## Section B — Peer Assessments

Complete one subsection per teammate. Add or remove subsections to match your team size.
If your team has 2 members, complete B1 only. If 3 members, complete B1 and B2.

---

### B1. Assessment of Teammate 1

| Field | Your answer |
|-------|------------|
| Teammate's full name |黃士桓|
| Teammate's student ID |113403026|

#### What did this teammate deliver?

List the tasks, functions, files, or document sections that this teammate was the primary author of,
based on what you observed during the project (compare against the work allocation).

> *Your answer:*Teammate 1 was responsible for the relational database queries. They were the primary author of databases/relational/queries.py, implementing core SQL functions such as schedule lookups, fare calculations, and checking seat availability (query_national_rail_availability, query_available_seats, etc.).

#### Did their actual contribution match the agreed work allocation?

> *Your answer (Yes / Mostly / Partially / No — with explanation):*Mostly，They completed the core SQL functions, though I stepped in to help implement and debug some of the more complex queries in queries.py to ensure we met the deadline and atomic transaction requirements.

#### Peer rating for this teammate

| Criterion | Rating (1–5) | Justification (1–2 sentences) |
|-----------|-------------|-------------------------------|
| Delivered the tasks assigned in the work allocation |4|Delivered the main SQL queries, with some assistance required for edge cases.|
| Quality of their work was satisfactory |3|The SQL logic was generally sound and followed the RealDictCursor pattern.|
| Communicated well and kept the team informed |4|Maintained good communication during the query implementation phase.|
| Met deadlines agreed within the team |4|Completed their portion in a timely manner.|
| **Overall rating for this teammate** |4|Solid contribution that fulfilled their core responsibilities.|

#### Estimated contribution percentage for this teammate

> My estimate of their contribution: **30%**

---

### B2. Assessment of Teammate 2

| Field | Your answer |
|-------|------------|
| Teammate's full name |林于翔|
| Teammate's student ID |113403540|

#### What did this teammate deliver?

> *Your answer:*Teammate 2 was responsible for the Graph Database (Neo4j) architecture and seeding. They analyzed the station JSON data, defined the graph schema (Node labels and Relationship types), updated the AI_SESSION_CONTEXT.md, and authored skeleton/seed_neo4j.py

#### Did their actual contribution match the agreed work allocation?

> *Your answer (Yes / Mostly / Partially / No — with explanation):*Mostly. They successfully designed and seeded the initial graph database. However, they missed the strict naming conventions required by the grading rubric (using CONNECTED_TO instead of METRO_LINK), which I had to discover and fix later during final testing.

#### Peer rating for this teammate

| Criterion | Rating (1–5) | Justification (1–2 sentences) |
|-----------|-------------|-------------------------------|
| Delivered the tasks assigned in the work allocation |4|Delivered the graph topology and seeding scripts as planned.|
| Quality of their work was satisfactory |3|The logic was correct, though some relationship naming conventions needed fixing.|
| Communicated well and kept the team informed |5|Excellent communication, especially when updating the AI_SESSION_CONTEXT.md before coding.|
| Met deadlines agreed within the team |5|Delivered their graph seeding scripts on schedule.|
| **Overall rating for this teammate** |4|Good effort in tackling the Neo4j network design.|

#### Estimated contribution percentage for this teammate

> My estimate of their contribution: **20%**

---

## Section C — Contribution Percentage Summary

All members (including yourself) must sum to 100%.

| Member | Your estimated % | Notes |
|--------|----------------|-------|
| Yourself | 50% |Handled Schema, PostgreSQL Seed, Vector DB, agent, PostgreSQL Queries, Graph Queries and final bug fixes.|
| Teammate 1 | 30% |Handled PostgreSQL Queries, Graph Queries.|
| Teammate 2 | 20% |Handled Graph DB Schema .|
| **Total** | **100%** | |

---

## Section D — Overall Team Reflection

### D1. What went well in the team's collaboration?

> *Your answer (2–4 sentences):*We strictly followed the "Schema-First Rule" as recommended in the workflow guide
. By agreeing on the PostgreSQL tables and Neo4j node labels first, and documenting them in AI_SESSION_CONTEXT.md
, we minimized conflicts when generating code with AI. Splitting the databases into distinct roles (Relational, Graph) also allowed us to work in parallel efficiently.

---

### D2. What would you do differently if you did this project again?

> *Your answer (2–4 sentences):*If I did this project again, I would design a more comprehensive booking system. Currently, the execute_booking function only processes single-leg national rail journeys. I would expand the relational schema to support a "Shopping Cart" or multi-leg itineraries, allowing users to book return tickets or group travel in a single atomic transaction. Furthermore, I would integrate the discount logic directly into the PostgreSQL database layer, ensuring that rules like "group booking discounts" from our policy documents are automatically calculated and applied during checkout.

---

### D3. Is there anything else the markers should know about team dynamics or individual contributions?

This is optional. Use it only if there is important context that the ratings above do not capture
(e.g., a member had a documented personal emergency, or a member was unresponsive for a significant period).

> *Your answer (or "Nothing to add"):*

---

## Declaration

I confirm that this peer review reflects my honest and independent assessment.
I understand it will be kept confidential from my teammates.

**Signed:** 陳昱翔 **Date:** 06-12