# ptxdist-repology

Repology JSON for PTXdist, see result here: [PTXdist repository information - Repology](https://repology.org/repository/ptxdist)

**JSON output:**

I will update the [`repology.json`](https://github.com/baxeno/ptxdist-repology/blob/main/repology.json) file in this repository at least once a month but likely more often.
PTXdist releases every month using `YYYY.MM.bugfix` versioning, so used a tagged version and not raw git commit.

> Note: Initial version was `2024.12.0`, see git history for more info.

**Usage:**

Generate latest repology.json for ptxdist.

```bash
echo "Setup local environment for generating repology.json"
toolbox create --distro fedora --release 42 ptxdist-env
toolbox enter ptxdist-env
sudo dnf install autoconf automake make gcc ncurses-devel flex bison texinfo patch gcc-c++
./repology.sh master
```

