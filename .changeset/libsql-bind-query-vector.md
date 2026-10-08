---
'@mastra/libsql': patch
---

Fixed slow `LibSQLVector.query()` searches when the vector index is not used, for example with in-memory databases, tables without a vector index, or filtered searches that fall back to checking every row. These searches return the same results but are much faster: with 5,000 vectors of 2,560 dimensions, an unfiltered search now takes about 50 ms instead of about 7 s.
