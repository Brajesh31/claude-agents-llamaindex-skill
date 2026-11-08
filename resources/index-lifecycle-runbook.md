# LlamaIndex Index Lifecycle Runbook

Use this runbook to operate an index after initial ingestion. The exact update and deletion APIs depend on the storage backend and LlamaIndex version.

## 1. Index Inventory

Record:

- **Index name and version:**
- **Storage backend:**
- **Embedding model and version:**
- **Embedding dimensions:**
- **Source systems:**
- **Document and node counts:**
- **Metadata schema:**
- **Access-control model:**
- **Owner:**
- **Last successful refresh:**

## 2. Scheduled Refresh

1. Identify changed, new, and deleted source records.
2. Fetch source content using approved connector credentials.
3. Parse and transform the content consistently.
4. Preserve stable document identifiers and metadata.
5. Rebuild or update affected nodes according to the storage backend's supported method.
6. Confirm that old versions are not returned unexpectedly.
7. Run a fixed set of validation queries.
8. Record counts, errors, and refresh duration.

## 3. Update and Duplicate Handling

- Use stable identifiers to recognize existing source records.
- Ensure repeated ingestion does not create duplicate nodes.
- Record source modification time or version.
- Define how changed content replaces or supersedes old content.
- Revalidate embeddings when the embedding model changes.
- Avoid mixing incompatible vector dimensions in one index.

## 4. Deletion and Access Changes

When a source document is deleted or access is revoked:

1. Identify all indexed nodes derived from the source.
2. Remove or invalidate those nodes using the supported storage API.
3. Check caches and derived indexes for copies.
4. Verify that retrieval no longer returns the content.
5. Confirm that unauthorized users cannot access the source through another query path.
6. Record completion evidence.

## 5. Versioning and Rollback

- Keep a known-good index version or reproducible snapshot where practical.
- Record ingestion code, parser, chunking, embedding, and index configuration.
- Validate a new index before switching production traffic.
- Define how to route back to the prior index if retrieval quality regresses.
- Ensure rollback does not reintroduce deleted or unauthorized content.

## 6. Health Checks

- [ ] Ingestion job completes within expected time.
- [ ] Document and node counts are within expected ranges.
- [ ] Failed records are reviewed.
- [ ] Sample queries retrieve the expected current source.
- [ ] Permission filters are enforced.
- [ ] Deleted records are no longer retrievable.
- [ ] Retrieval latency and errors are monitored.
- [ ] Index version and last refresh are visible to operators.

## Change Record

- **Change / refresh ID:**
- **Index before:**
- **Index after:**
- **Sources changed:**
- **Validation queries:**
- **Errors and skipped records:**
- **Rollback reference:**
- **Operator and date:**
