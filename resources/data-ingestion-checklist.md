# LlamaIndex Data Ingestion Checklist

Use this checklist when onboarding a new source or changing an ingestion pipeline.

## Source and Access

- [ ] Source system and owner are identified.
- [ ] Permission to ingest and index the content is confirmed.
- [ ] Connector package and version are recorded.
- [ ] Credentials are stored securely and have minimum required scope.
- [ ] Source rate limits and pagination behavior are understood.
- [ ] Tenant or user access boundaries are documented.

## Loading and Parsing

- [ ] Representative files and formats are tested.
- [ ] Parser handles encoding and malformed files safely.
- [ ] Tables, headings, page boundaries, and other useful structure are preserved.
- [ ] Empty or unsupported documents are reported.
- [ ] Duplicate source records are detected.
- [ ] Document size and ingestion time are measured.

## Metadata and Identity

- [ ] Each document has a stable source identifier.
- [ ] Metadata includes source, owner or tenant, timestamps, and version where required.
- [ ] Access-control metadata is retained and enforced during retrieval.
- [ ] Metadata fields are consistently typed and named.
- [ ] Sensitive metadata is not unnecessarily exposed to the model.

## Transformation and Chunking

- [ ] Normalization does not remove meaning-bearing information.
- [ ] Chunk boundaries preserve relevant context.
- [ ] Chunk size and overlap are justified by the document type and query patterns.
- [ ] Parent-child or document relationship metadata is preserved when used.
- [ ] Chunking is tested on long, short, and structured documents.

## Indexing

- [ ] Embedding model and dimensions are recorded.
- [ ] Index configuration is versioned.
- [ ] Re-ingestion behavior is idempotent.
- [ ] Failed documents can be retried without duplicating records.
- [ ] A sample query retrieves expected source passages.

## Completion Record

- **Source:**
- **Connector and version:**
- **Document count:**
- **Failed / skipped count:**
- **Index version:**
- **Validation queries:**
- **Known gaps:**
- **Owner and date:**
