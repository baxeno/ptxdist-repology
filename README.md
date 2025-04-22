# ptxdist-repology

Repology JSON for PTXdist

**Usage:**

Apply out-of-tree changes to ptxdist, see [branch `repology_support_v2` in `baxeno/ptxdist`](https://github.com/baxeno/ptxdist/tree/repology_support_v2).

```bash
ptxdist repology | grep -v "make: Nothing to be done for" > repology.json
```

**JSON output:**

I will update the [`repology.json`](https://github.com/baxeno/ptxdist-repology/blob/main/repology.json) file in this repository every month when a new PTXdist version is released.

> Note: Initial version was `2024.12.0`, see git history for more info.

