# ptxdist-repology

Repology JSON for PTXdist, see result here: [PTXdist repository information - Repology](https://repology.org/repository/ptxdist)

**JSON output:**

I will update the [`repology.json`](https://github.com/baxeno/ptxdist-repology/blob/main/repology.json) file in this repository at least once a month but likely more often.
PTXdist releases every month using `YYYY.MM.bugfix` versioning, so used a tagged version and not raw git commit.

> Note: Initial version was `2024.12.0`, see git history for more info.

**Status:**

Upstream support in PTXdist is ongoing:

- [[ptxdist] [PATCH v3] ptxdist: add repology json output support](https://www.mail-archive.com/ptxdist@pengutronix.de/msg26235.html)
- [[ptxdist] [PATCH v2] ptxdist: add repology json output support](https://www.mail-archive.com/ptxdist@pengutronix.de/msg26107.html)
- [[ptxdist] [PATCH] ptxdist: add repology json output support](https://www.mail-archive.com/ptxdist@pengutronix.de/msg25354.html)
- [[ptxdist] [RFC PATCH] ptxdist: add repology sub command](https://www.mail-archive.com/ptxdist@pengutronix.de/msg25341.html)

Upstream support in repology-updater is done:

- [Add PTXdist support #1487](https://github.com/repology/repology-updater/issues/1487)
- [parsers: add ptxdist support](https://github.com/repology/repology-updater/pull/1488)

**Usage:**

Apply out-of-tree changes to ptxdist, see [branch `repology` in `baxeno/ptxdist`](https://github.com/baxeno/ptxdist/tree/repology) or [PATCH v3](v3-0001-ptxdist-add-repology-json-output-support.patch).

```bash
echo "Setup local environment for generating repology.json"
# Start toolbox Fedora
# Install dependencies
# git clone Distrokit
# git clone PTXdist
# cd ptxdist
# git checkout -b repology && git am v3-0001-ptxdist-add-repology-json-output-support.patch
# ./autogen.sh && ./configure && make
# cd Distrokit
# ln -sf ../ptxdist/bin/ptxdist ptxdist
# select toolchain + ptxconfig + platformconfig
# ptxdist repology > repology.json

echo "Using existing local environment for generating repology.json"
toolbox enter
cd ptxdist
git checkout master
git pull
git checkout repology
./autogen.sh && ./configure && make
cd ../DistroKit
ptxdist repology > ../ptxdist-repology/repology.json
```

