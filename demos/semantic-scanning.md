# Semantic Scanning Demo

## Targeted JSON Extraction Performance

**Claim**: Event-driven scanning beats DOM parsing for focused field extraction.

## Benchmark Results

```
METHOD              TIME (108K events)
DOM Parse + Query   287ms
Pounce Scan         99ms
```

**2.9× speedup** for targeted field extraction.

## Key Metrics

- **108,341 events processed** in validation corpus
- **Zero-copy spans**: No intermediate string allocations
- **Bounded memory**: Fixed overhead regardless of document size
- **Deterministic hashing**: SHA-256 verified output consistency

## Technical Innovation

1. **Event-driven architecture**: Process JSON as a stream of events, not a tree
2. **Selective materialization**: Only extract fields matching probe criteria
3. **Early termination**: Stop parsing when all required fields found
4. **Zero-copy extraction**: Return spans into original buffer, no copies

## Use Cases

- **Log processing**: Extract specific fields from JSONL streams
- **API response filtering**: Forward only required fields to downstream
- **Schema validation**: Verify structure without full parse
- **Cost reduction**: Avoid tokenizing irrelevant content


---

Notes

- This public repo is narrative-only; detailed reproduction steps and implementation details are available post-NDA.
