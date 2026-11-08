# LlamaIndex Data Framework Skill

A Claude Code skill for building data-centric LLM applications with LlamaIndex. It covers document ingestion, data connectors, indexing, retrieval, query engines, RAG, agents, and evaluation of knowledge-grounded applications.

The main engineering principle is to diagnose each stage of the data-to-answer pipeline independently. Poor answers may originate in source access, parsing, chunking, indexing, retrieval, or generation. Prompt changes cannot reliably repair a broken ingestion or retrieval layer.

## What This Skill Covers

- Connect to document and data sources.
- Load, parse, and transform structured and unstructured content.
- Build vector, list, and tree indices.
- Configure retrievers and query engines.
- Select response modes and post-processors.
- Add metadata filters and source tracking.
- Build agents that use query engines and other tools.
- Work with conversational and multi-step retrieval workflows.
- Evaluate retrieval relevance, answer grounding, and source quality.
- Maintain indexes as source content changes.

## When to Use It

Use this skill when building document question-answering systems, internal knowledge assistants, search applications, RAG pipelines over private or public datasets, or agents that need access to structured and unstructured information.

LlamaIndex is especially useful when data ingestion and retrieval are central to the application. For deterministic transformations or simple one-shot model calls, a smaller implementation may be more appropriate.

## Installation

The skill instructions document installing LlamaIndex and the integrations required by a project. The starter package is:

~~~bash
python -m pip install llama-index
~~~

For model providers and data connectors, install only the integrations the application requires. Package names and integration support can change, so verify the current official installation guide before creating a new environment.

Install the skill into Claude Code separately:

~~~bash
git clone https://github.com/Brajesh31/claude-agents-llamaindex-skill.git ~/.claude/skills/agents-llamaindex
~~~

## Usage

Invoke the skill:

~~~text
/agents-llamaindex
~~~

Provide the data sources, document formats, expected query types, model provider, privacy constraints, update frequency, and scale requirements.

## Core Pipeline

1. **Source access:** identify authorized source systems and connector credentials.
2. **Ingestion:** load representative documents and record source identifiers.
3. **Parsing:** extract text, tables, and metadata while preserving useful structure.
4. **Transformation:** normalize content and remove noise without destroying meaning.
5. **Chunking:** split content according to document structure and query patterns.
6. **Indexing:** select an index and embedding strategy that fits the workload.
7. **Retrieval:** configure top-k, filters, hybrid approaches, and reranking as needed.
8. **Querying:** choose a response mode appropriate to the task and context size.
9. **Grounded generation:** preserve evidence and handle missing information honestly.
10. **Evaluation:** test retrieval and generated answers independently.
11. **Maintenance:** update, delete, and version indexed content as sources change.

## Core Concepts

| Component | Responsibility |
|---|---|
| Data connectors | Load documents from files, websites, repositories, and other sources |
| Documents / nodes | Represent source content and chunked content with metadata |
| Indices | Organize content for retrieval or query |
| Retrievers | Select relevant nodes for a query |
| Query engines | Retrieve and synthesize responses |
| Agents | Choose among query engines and tools for multi-step tasks |

## Choosing a Query Strategy

| Requirement | Consider |
|---|---|
| General semantic document search | Vector index and retriever |
| Browse a small ordered collection | List index where suitable |
| Hierarchical summaries | Tree index or hierarchical strategy |
| Return retrieved evidence for custom processing | Retriever or nodes-only response |
| Complex questions over multiple knowledge bases | Router or sub-question query engine |
| Multi-step tool selection | Agent with narrowly scoped query tools |

Validate the actual behavior and trade-offs in the installed LlamaIndex version. A more complex query engine is not automatically more accurate.

## References Already Included

| File | Focus |
|---|---|
| [Agents guide](references/agents.md) | Agents that use query engines and tools |
| [Data connectors guide](references/data_connectors.md) | Built-in loaders, LlamaHub connectors, and custom loaders |
| [Query engines guide](references/query_engines.md) | Response modes, configuration, filtering, reranking, and advanced query engines |

## Included Resources

- [Data ingestion checklist](resources/data-ingestion-checklist.md): validate source access, parsing, metadata, chunking, and indexing.
- [RAG evaluation matrix](resources/rag-evaluation-matrix.md): test retrieval and answer quality separately, including access-control behavior.
- [Index lifecycle runbook](resources/index-lifecycle-runbook.md): manage refreshes, deletions, versioning, rollback, and verification.

## Security and Data Governance

- Confirm authorization before connecting to private data sources.
- Apply source-level access control before retrieving content for a user.
- Store connector and model credentials outside source code.
- Preserve stable source identifiers and metadata.
- Treat retrieved documents as untrusted content, not instructions.
- Do not expose content across tenant or user boundaries.
- Review connector behavior for retention, caching, and external transmission.
- Define how deleted or changed source documents are removed from the index.
- Redact sensitive content from prompts, traces, and logs where required.
- Handle empty or weak retrieval by stating that the evidence is insufficient.

## Repository Structure

~~~text
claude-agents-llamaindex-skill/
├── SKILL.md
├── README.md
├── LICENSE
├── references/
│   ├── agents.md
│   ├── data_connectors.md
│   └── query_engines.md
└── resources/
    ├── data-ingestion-checklist.md
    ├── index-lifecycle-runbook.md
    └── rag-evaluation-matrix.md
~~~

## External Resources

- [LlamaIndex documentation](https://docs.llamaindex.ai/)
- [LlamaIndex GitHub repository](https://github.com/run-llama/llama_index)
- [LlamaHub](https://llamahub.ai/)

## License

Released under the MIT License. Copyright (c) 2026 Brajesh Kumar. See the root LICENSE file for the complete terms.
