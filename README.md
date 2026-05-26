I lead technical teams in biotech and write software for new genomics technologies. At Fulcrum Genomics you'll find me building tools and leading others in the fields of oncology, cell & gene editing, and precision medicine all while ensuring we deliver high-quality services to our clients and partners.

![Cover](.github/img/cover.jpg)

## Featured

| Project | Stack | What it does |
|---|---|---|
| [chum](https://github.com/clintval/chum) | [![Language](https://img.shields.io/badge/language-rust-dea588.svg)](https://www.rust-lang.org/) | Evaluate baits in a hybrid selection panel. |
| [krak](https://github.com/clintval/krak) | [![Language](https://img.shields.io/badge/language-rust-dea588.svg)](https://www.rust-lang.org/) | An addicting set of Kraken-enhancing tools. |
| [vartovcf](https://github.com/clintval/vartovcf) | [![Language](https://img.shields.io/badge/language-rust-dea588.svg)](https://www.rust-lang.org/) | Stream VarDict variants into VCF v4.2. |
| [neodisambiguate](https://github.com/clintval/neodisambiguate) | [![Language](https://img.shields.io/badge/language-scala-c22d40.svg)](https://www.scala-lang.org/) | Disambiguate reads mapped to multiple references. |
| [bedspec](https://github.com/clintval/bedspec) | [![Language](https://img.shields.io/badge/language-python-blue.svg)](https://www.python.org/) | An HTS-specs compliant BED toolkit. |
| [typeline](https://github.com/clintval/typeline) | [![Language](https://img.shields.io/badge/language-python-blue.svg)](https://www.python.org/) | Dataclasses to delimited text, round-trip with types. |

## neodisambiguate

Disambiguate templates aligned to human and mouse references:

```bash
❯ pixi exec --channel bioconda --channel conda-forge \
    neodisambiguate \
        --input dna00001.aligned-to-human.bam dna00001.aligned-to-mouse.bam \
        --output out/dna00001 \
        --names hg38 mm10
```

## chum

Score capture baits against a reference:

```bash
❯ pixi exec --channel bioconda --channel conda-forge \
    chum score \
        --baits baits.fa \
        --targets targets.bed \
        --reference hg38.fa \
        --per-bait per-bait.tsv
```

### Elsewhere

- LinkedIn: <https://www.linkedin.com/in/clint-valentine/>
- Fulcrum Genomics: <https://fulcrumgenomics.com>
- Bioconda recipes: <https://bioconda.github.io/search.html?q=clintval>
- PyPI packages: <https://pypi.org/user/clintval/>
