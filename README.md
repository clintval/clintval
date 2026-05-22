# clintval

I lead technical teams in biotech and write software for new genomics technologies. At Fulcrum Genomics you'll find me building tools and leading others in the fields of oncology, cell & gene editing, and precision medicine all while ensuring we deliver high-quality services to our clients and partners.

![Cover](.github/img/cover.jpg)

## Featured

| Project | Stack | What it does |
|---|---|---|
| [chum](https://github.com/clintval/chum) | Rust | Evaluate baits in a hybrid selection panel. |
| [krak](https://github.com/clintval/krak) | Rust | An addicting set of Kraken-enhancing tools. |
| [vartovcf](https://github.com/clintval/vartovcf) | Rust | Stream VarDict variants into VCF v4.2. |
| [neodisambiguate](https://github.com/clintval/neodisambiguate) | Scala | Disambiguate reads mapped to multiple references. |
| [bedspec](https://github.com/clintval/bedspec) | Python | An HTS-specs compliant BED toolkit. |
| [typeline](https://github.com/clintval/typeline) | Python | Dataclasses to delimited text, round-trip with types. |

## Examples

Score capture baits against a reference:

```bash
❯ pixi exec -c bioconda -c conda-forge \
    chum score \
        --baits baits.fa \
        --targets targets.bed \
        --reference hg38.fa \
        --per-bait per-bait.tsv
```

Bridge Kraken classifications into a BAM and filter by taxon:

```bash
❯ krak annotate \
      -i input.bam \
      -d /kraken-db \
      -a <(krak prep input.bam | kraken2 --db /kraken-db --output - -) \
  | krak filter -t 9606 -o output.bam
```

Stream VarDict calls straight into a sorted, compressed VCF:

```bash
❯ vardict-java -b in.bam -G hg38.fa -N s1 -f0.05 calls.bed \
  | vartovcf --reference hg38.fa --sample s1 \
  | bcftools sort -Oz > variants.vcf.gz
```

Disambiguate templates aligned to human and mouse references:

```bash
❯ neodisambiguate \
      -i dna00001.A.bam dna00001.B.bam \
      -o out/dna00001 \
      -n hg38 mm10
```

### Elsewhere

- Fulcrum Genomics: <https://fulcrumgenomics.com>
- Bioconda recipes: <https://bioconda.github.io/search.html?q=clintval>
- PyPI packages: <https://pypi.org/user/clintval/>
