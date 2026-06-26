<img src=".github/img/cover.jpg" alt="Cover" width="100%">

I lead technical teams in biotech and write software for new genomics technologies. At Fulcrum Genomics you'll find me building tools and leading others in the fields of oncology, cell & gene editing, and precision medicine all while ensuring we deliver high-quality services to our clients and partners.

## Featured

<table width="100%">
<thead>
<tr><th>Project</th><th>Stack</th><th>Install</th><th>What it does</th></tr>
</thead>
<tbody>
<tr>
<td><a href="https://github.com/clintval/unmux">unmux</a></td>
<td><a href="https://www.rust-lang.org/"><img alt="Language" src="https://img.shields.io/badge/language-rust-dea588.svg"></a></td>
<td><a href="http://bioconda.github.io/recipes/unmux/README.html"><img alt="Install with bioconda" src="https://img.shields.io/badge/Install%20with-bioconda-brightgreen.svg"></a></td>
<td>Parse and demultiplex records, splitcode-style.</td>
</tr>
<tr>
<td><a href="https://github.com/clintval/chum">chum</a></td>
<td><a href="https://www.rust-lang.org/"><img alt="Language" src="https://img.shields.io/badge/language-rust-dea588.svg"></a></td>
<td><a href="http://bioconda.github.io/recipes/chum/README.html"><img alt="Install with bioconda" src="https://img.shields.io/badge/Install%20with-bioconda-brightgreen.svg"></a></td>
<td>Evaluate baits in a hybrid selection panel.</td>
</tr>
<tr>
<td><a href="https://github.com/clintval/krak">krak</a></td>
<td><a href="https://www.rust-lang.org/"><img alt="Language" src="https://img.shields.io/badge/language-rust-dea588.svg"></a></td>
<td><a href="http://bioconda.github.io/recipes/krak/README.html"><img alt="Install with bioconda" src="https://img.shields.io/badge/Install%20with-bioconda-brightgreen.svg"></a></td>
<td>An addicting set of Kraken-enhancing tools.</td>
</tr>
<tr>
<td><a href="https://github.com/clintval/vartovcf">vartovcf</a></td>
<td><a href="https://www.rust-lang.org/"><img alt="Language" src="https://img.shields.io/badge/language-rust-dea588.svg"></a></td>
<td><a href="http://bioconda.github.io/recipes/vartovcf/README.html"><img alt="Install with bioconda" src="https://img.shields.io/badge/Install%20with-bioconda-brightgreen.svg"></a></td>
<td>Stream VarDict variants into VCF v4.2.</td>
</tr>
<tr>
<td><a href="https://github.com/clintval/neodisambiguate">neodisambiguate</a></td>
<td><a href="https://www.scala-lang.org/"><img alt="Language" src="https://img.shields.io/badge/language-scala-c22d40.svg"></a></td>
<td><a href="http://bioconda.github.io/recipes/neodisambiguate/README.html"><img alt="Install with bioconda" src="https://img.shields.io/badge/Install%20with-bioconda-brightgreen.svg"></a></td>
<td>Disambiguate reads mapped to multiple references.</td>
</tr>
<tr>
<td><a href="https://github.com/clintval/bedspec">bedspec</a></td>
<td><a href="https://www.python.org/"><img alt="Language" src="https://img.shields.io/badge/language-python-blue.svg"></a></td>
<td><a href="https://badge.fury.io/py/bedspec"><img alt="PyPi Release" src="https://badge.fury.io/py/bedspec.svg"></a></td>
<td>An HTS-specs compliant BED toolkit.</td>
</tr>
<tr>
<td><a href="https://github.com/clintval/typeline">typeline</a></td>
<td><a href="https://www.python.org/"><img alt="Language" src="https://img.shields.io/badge/language-python-blue.svg"></a></td>
<td><a href="https://badge.fury.io/py/typeline"><img alt="PyPi Release" src="https://badge.fury.io/py/typeline.svg"></a></td>
<td>Dataclasses to delimited text, round-trip with types.</td>
</tr>
</tbody>
</table>

## unmux

Demultiplex a dual-index paired-end run against a sample sheet, routing each read pair by its i7+i5 barcode concatenation:

```bash
❯ unmux "R1.fastq.gz" "I1.fastq.gz" "I2.fastq.gz" "R2.fastq.gz" \
  --extract "i7=1:0:8" \
  --extract "i5=2:0:8" \
  --extract "r1=0:0:end" \
  --extract "r2=3:0:end" \
  --group "samples=metadata.tsv" \
  --group "samples::match=i7+i5" \
  --template "r1" \
  --template "r2" \
  --sample-from-group "samples" \
  --out "demux/%sample.R%ordinal.fq"
```

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

[![LinkedIn](https://img.shields.io/badge/LinkedIn-clint--valentine-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/clint-valentine/)
[![Fulcrum Genomics](https://img.shields.io/badge/Fulcrum%20Genomics-website-1f6feb)](https://fulcrumgenomics.com)
[![Bioconda](https://img.shields.io/badge/Bioconda-recipes-brightgreen?logo=anaconda&logoColor=white)](https://bioconda.github.io/search.html?q=clintval)
[![PyPI](https://img.shields.io/badge/PyPI-packages-3775A9?logo=pypi&logoColor=white)](https://pypi.org/user/clintval/)
