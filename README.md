# archive-codec

> Recursive archive walking for the [documents.js family](https://github.com/ExaDev): detects ZIP-in-ZIP entries, walks them recursively under explicit depth and total-decompressed-size caps (zip-bomb guards), and returns a flat listing of every inner entry with its ancestor chain. Zero document-format knowledge; Worker-isomorphic (the same code runs under Node and inside a Cloudflare Workers isolate).

```ts
import { walkArchive } from 'archive-codec';

// Every entry of every nested ZIP, flattened; throws if the walk exceeds
// the depth cap or the cumulative decompressed-bytes budget.
for (const entry of walkArchive(docxBytes)) {
  entry.path;      // e.g. 'xl/workbook.xml' within its own archive
  entry.ancestors; // e.g. ['word/embeddings/oleObject1.xlsx'] -- the nested
                   // ZIP entries descended through to reach this one
  entry.bytes;     // decompressed content
}
```

Scope for v1: ZIP containers only (read and write, over [fflate](https://github.com/101arrowz/fflate)); tar and gzip are explicitly out of scope. MIT licensed.
