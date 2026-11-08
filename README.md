# LlamaIndex Agents Skill

A Claude skill for building context-aware LLM applications with LlamaIndex. It focuses on agents, data connectors, and query engines, helping developers connect source data to retrieval and agent workflows.

## What This Skill Covers

- Understanding agent workflows built with LlamaIndex.
- Connecting documents and external data sources.
- Preparing data for indexing and retrieval.
- Selecting and configuring query engines.
- Combining retrieval with agent capabilities.
- Structuring an application around the data and questions it needs to support.

## Repository Structure

- `SKILL.md`: Main skill instructions and framework overview.
- `references/agents.md`: Additional guidance on LlamaIndex agents.
- `references/data_connectors.md`: Reference material for connecting and ingesting data.
- `references/query_engines.md`: Guidance for query-engine concepts and workflows.
- `LICENSE`: MIT License for this repository.

## When to Use It

Use this skill when building an application that needs to ingest external information, index it, retrieve relevant context, and answer questions over that data. It is also useful when evaluating how agent behaviour should interact with data connectors and query engines.

## Getting Started

1. Read `SKILL.md` for the main concepts and recommended workflow.
2. Identify the data sources the application needs to access.
3. Choose and configure the appropriate connectors.
4. Prepare and index the data for retrieval.
5. Select a query engine that matches the application's retrieval needs.
6. Add agent behaviour only where it provides value beyond a direct query workflow.
7. Test retrieval and response quality with representative questions.

## Implementation Guidance

Treat ingestion, indexing, retrieval, and response generation as separate stages when debugging. Validate that the correct data is available to the query engine before changing prompts or model settings. Keep connectors and query logic aligned with the data sources and use cases the application actually supports.

## License

Released under the MIT License. See [LICENSE](LICENSE) for details.
