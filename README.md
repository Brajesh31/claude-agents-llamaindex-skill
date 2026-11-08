# claude-agents-llamaindex-skill

A Claude Code skill for building data-centric LLM applications with LlamaIndex, including ingestion, indexing, retrieval, query engines, and agent workflows.

## Overview

LlamaIndex provides building blocks for connecting language models to external data. This skill helps design retrieval-augmented generation (RAG) systems, prepare documents, create indexes, query knowledge collections, and add agent behavior where it improves the application.

## Main Capabilities

- Connect to document and data sources.
- Ingest, parse, and transform content.
- Build indexes for retrieval.
- Select vector, keyword, or hybrid retrieval patterns.
- Configure query engines and response synthesis.
- Build agents that use data tools.
- Combine retrieval with multi-step reasoning.
- Evaluate retrieval quality and answer grounding.

## When to Use It

Use this skill when building:

- Document question-answering systems.
- Internal knowledge assistants.
- Search and retrieval applications.
- RAG pipelines over private datasets.
- Agents that need access to structured or unstructured information.
- Multimodal data applications where supported.

## Installation

Install the LlamaIndex packages required by the project, then clone the skill:

```bash
git clone https://github.com/Brajesh31/claude-agents-llamaindex-skill.git ~/.claude/skills/agents-llamaindex
```

Package selection depends on the data connectors, model provider, and index types used. Avoid installing every integration when only a subset is needed.

## Usage

Invoke the skill when designing or implementing a LlamaIndex workflow:

```text
/agents-llamaindex
```

Provide the data sources, document formats, expected query types, model environment, privacy constraints, and scale requirements.

## Recommended RAG Workflow

1. Identify the data sources and access permissions.
2. Ingest representative documents.
3. Parse and normalize content.
4. Split documents into appropriate chunks.
5. Attach stable metadata and identifiers.
6. Build the selected index.
7. Configure retrieval and ranking.
8. Generate answers with relevant context.
9. Evaluate retrieval and answer quality.
10. Monitor freshness, latency, and failure cases.

## Agent Design

Add an agent only when the workflow requires decisions or tool selection beyond a direct retrieval query. Keep tool contracts narrow, validate inputs, and define which operations require approval.

## Reference Guide

| File | Purpose |
|---|---|
| `references/agents.md` | Agent workflows and tool use |
| `references/data_connectors.md` | Data ingestion and connectors |
| `references/query_engines.md` | Query engine design and retrieval |

## Quality Checklist

- Ingestion respects source permissions.
- Documents retain useful metadata.
- Chunking preserves relevant context.
- Retrieval returns evidence relevant to the question.
- Answers are grounded in retrieved material.
- Empty or weak retrieval results are handled honestly.
- Index updates and deletions are managed.
- Evaluation includes representative and adversarial questions.
- Sensitive source content is not exposed to unauthorized users.

## Repository Contents

- `SKILL.md`: Main LlamaIndex skill instructions.
- `references/`: Agent, connector, and query-engine guidance.
- `README.md`: Setup, RAG workflow, and quality checklist.

## Practical Guidance

Do not tune prompts to compensate for broken ingestion or poor retrieval. Diagnose each stage separately: source access, parsing, chunking, indexing, retrieval, and answer generation.
