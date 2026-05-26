![Cover](.github/img/cover.jpg)

I lead technical teams in biotech and write software for new genomics technologies. At Fulcrum Genomics you'll find me building tools and leading others in the fields of oncology, cell & gene editing, and precision medicine all while ensuring we deliver high-quality services to our clients and partners.

## Featured

| Project | Stack | Install | What it does |
|---|---|---|---|
| [chum](https://github.com/clintval/chum) | [![Language](https://img.shields.io/badge/language-rust-dea588.svg)](https://www.rust-lang.org/) | [![Install with bioconda](https://img.shields.io/badge/Install%20with-bioconda-brightgreen.svg)](http://bioconda.github.io/recipes/chum/README.html) | Evaluate baits in a hybrid selection panel. |
| [krak](https://github.com/clintval/krak) | [![Language](https://img.shields.io/badge/language-rust-dea588.svg)](https://www.rust-lang.org/) | [![Install with bioconda](https://img.shields.io/badge/Install%20with-bioconda-brightgreen.svg)](http://bioconda.github.io/recipes/krak/README.html) | An addicting set of Kraken-enhancing tools. |
| [vartovcf](https://github.com/clintval/vartovcf) | [![Language](https://img.shields.io/badge/language-rust-dea588.svg)](https://www.rust-lang.org/) | [![Install with bioconda](https://img.shields.io/badge/Install%20with-bioconda-brightgreen.svg)](http://bioconda.github.io/recipes/vartovcf/README.html) | Stream VarDict variants into VCF v4.2. |
| [neodisambiguate](https://github.com/clintval/neodisambiguate) | [![Language](https://img.shields.io/badge/language-scala-c22d40.svg)](https://www.scala-lang.org/) | [![Install with bioconda](https://img.shields.io/badge/Install%20with-bioconda-brightgreen.svg)](http://bioconda.github.io/recipes/neodisambiguate/README.html) | Disambiguate reads mapped to multiple references. |
| [bedspec](https://github.com/clintval/bedspec) | [![Language](https://img.shields.io/badge/language-python-blue.svg)](https://www.python.org/) | [![PyPi Release](https://badge.fury.io/py/bedspec.svg)](https://badge.fury.io/py/bedspec) | An HTS-specs compliant BED toolkit. |
| [typeline](https://github.com/clintval/typeline) | [![Language](https://img.shields.io/badge/language-python-blue.svg)](https://www.python.org/) | [![PyPi Release](https://badge.fury.io/py/typeline.svg)](https://badge.fury.io/py/typeline) | Dataclasses to delimited text, round-trip with types. |

## chum

Score capture baits against a reference:

```bash
❯ chum score \
    --baits baits.fa \
    --targets targets.bed \
    --reference hg38.fa \
    --per-bait per-bait.tsv
```

## krak

Bridge Kraken classifications into a BAM and filter by taxon:

```bash
❯ krak annotate \
      -i input.bam \
      -d /kraken-db \
      -a <(krak prep input.bam | kraken2 --db /kraken-db --output - -) \
  | krak filter -t 9606 -o output.bam
```

## neodisambiguate

Disambiguate templates aligned to human and mouse references:

```bash
❯ neodisambiguate \
    --input dna00001.aligned-to-human.bam dna00001.aligned-to-mouse.bam \
    --output out/dna00001 \
    --names hg38 mm10
```

### Elsewhere

- LinkedIn: <https://www.linkedin.com/in/clint-valentine/>
- Fulcrum Genomics: <https://fulcrumgenomics.com>
- Bioconda recipes: <https://bioconda.github.io/search.html?q=clintval>
- PyPI packages: <https://pypi.org/user/clintval/>
