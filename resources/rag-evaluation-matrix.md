# LlamaIndex RAG Evaluation Matrix

Measure retrieval and response generation separately. A fluent answer is not evidence that the right source passages were retrieved.

## Evaluation Configuration

- **Corpus / snapshot:**
- **Index version:**
- **Embedding model:**
- **Chunking strategy:**
- **Retriever and top-k:**
- **Filters and reranker:**
- **Query engine and response mode:**
- **Generation model:**
- **Evaluation date:**

## Test Questions

| ID | Question | Expected document / evidence | Required answer facts | Expected abstention? |
|---|---|---|---|---|
| Q01 | | | | |
| Q02 | | | | |
| Q03 | | | | |

Include direct questions, paraphrases, multi-document questions, ambiguous questions, no-answer questions, stale-data questions, and conflicting-source questions.

## Retrieval Results

| Measure | Definition | Result | Notes |
|---|---|---:|---|
| Recall@k | Relevant evidence appears in top k | | |
| Precision@k | Retrieved passages are relevant | | |
| Ranking quality | Most useful evidence ranks highly | | |
| Metadata filtering | Correct source / tenant / user boundary | | |
| Source freshness | Current version retrieved | | |
| Empty result behavior | No evidence is handled honestly | | |

## Answer Results

| Criterion | Pass condition | Result | Evidence |
|---|---|---|---|
| Correctness | Claims are supported by retrieved evidence | | |
| Completeness | Required facts are covered | | |
| Grounding | Unsupported details are not invented | | |
| Source attribution | Citations point to supporting content | | |
| Abstention | Insufficient evidence is stated clearly | | |
| Privacy | Unauthorized data is not exposed | | |

## Failure Categories

- **Connector:** content was not loaded or updated.
- **Parsing:** meaningful source structure was lost.
- **Chunking:** relevant context was split or omitted.
- **Metadata:** source identity, freshness, or permissions were lost.
- **Retrieval:** relevant passages were not selected or ranked.
- **Generation:** the model ignored or misrepresented the evidence.
- **Evaluation:** expected answer or scoring rule is unclear.

Record the query, retrieved nodes, metadata, answer, root cause, and proposed remediation for each significant failure.

## Release Gate

- [ ] Test set includes supported and unsupported questions.
- [ ] Retrieval and generation have separate scores.
- [ ] Permission and tenant isolation are tested.
- [ ] Citations are checked against source passages.
- [ ] Updates and deletions are reflected in retrieval.
- [ ] Dataset coverage and limitations are documented.
