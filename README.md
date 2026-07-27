# Technical case study: single-cell RNA-seq

A short, self-paced analysis exercise for candidates interviewing for the
bioinformatics engineer position.
---

## Start here

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/rekren/case_scrnaseq/blob/main/scRNAseq_case_study_R_and_Python.ipynb)

1. Open the notebook in Colab and choose **File > Save a copy in Drive**. Work in
   your copy.
2. Choose your track (see below) and set **Runtime > Change runtime type**
   accordingly, *before* running anything.
3. Run the first cell and work down. The data downloads itself.

Everything runs on the **free Colab tier with no GPU**. If you would rather work
on your own machine, the dataset is small enough for any laptop with 8 GB of RAM.

---

## What you will be working with

One dataset from a **perturbation experiment**: immune cells from peripheral
blood, profiled by droplet-based single-cell RNA sequencing, under **two
conditions** (`ctrl` and `stim`), with cells from **eight donors** contributing
to both. Roughly 24,700 cells and 15,700 genes, as raw UMI counts.

The object also carries some columns and embeddings from **an earlier analysis
of the same data**, prefixed `provided_` when the notebook loads. Treat those as
a colleague's unreviewed work rather than as ground truth. Deciding how much of
it you believe is part of the exercise.

---

## Choose one track

The notebook contains the same analysis twice. **Work through one section and
ignore the other.** The questions are identical in both, under the same numbers
Q1 to Q23, and they are marked identically.

| | Section 1 | Section 2 |
|---|---|---|
| Language | R, `Seurat` | Python, `scanpy` |
| Colab runtime | **R** | **Python 3** |
| Data file | `case_data.RDS` | `case_data.h5ad` |

Pick whichever you are faster in. The choice is **not scored** and there is no
hidden preference. For context only: the group is R-fluent and most routine
analysis here is written in R, so R is a natural default and you would be well
supported in it. Python is also valued, and not only for single-cell work. We
would rather read clear reasoning in your stronger language than hesitant code
in your weaker one.

---

## How this is assessed

**Not on package fluency.** Neither role assumes you have run this workflow
before, and every code cell already runs on sensible defaults, so nobody gets
stuck on syntax. The marks are in the written answers.

- **Reasoning.** Say *why*, not *what*. "I set the resolution to 0.5" is worth
  nothing; "I set it to 0.5 because 1.0 split cluster 3 without producing any
  distinguishing marker gene" is worth a great deal. For every conclusion, name
  the observation that would have pointed the other way.
- **Curiosity.** Several things in this dataset are odd, and at least one will
  not match what any tutorial told you to expect. We care more that you *notice*
  and *chase* them than that you resolve them.
- **Carrying your own modality across.** Several questions ask you to map a
  concept from the area of omics you already know onto this one, and to say
  where the analogy stops working. These need no single-cell background, only
  clear thinking about what you already understand.

**Speculate, and label it as speculation.** Most of these questions cannot be
settled from the data alone. "My best interpretation is X, because Y, and I
would test it by Z" is exactly the shape of answer we want. A labelled,
well-argued guess scores higher than silence and much higher than false
confidence. "I do not know, and here is how I would find out" is a complete
answer.

**Wrong answers defended with clear evidence score above right answers with no
justification.**

---

## Ground rules

1. **Time.** About 3 hours of focused work, plus an hour for the slides.
   If you run out of time, stop and write down what you would have done next.
   That answer is itself marked.
2. **Every question needs an answer**, two to six sentences. An empty box scores
   zero, and so does "used the default". If you tried something that failed, say
   so; that is a valid answer.
3. **Use any tool you like**, including documentation, forums and language
   models. If a tool wrote part of your answer, say which part and whether you
   checked it (Q22).
4. **One exception.** This is a public dataset and you may well recognise it,
   which is fine and costs you nothing. But please **do not go looking for it and
   do not read the original paper.** We are not testing whether you can retrieve
   a published answer. If you recognise it, say so in Q22 and carry on reasoning
   from the matrix.

---

## Submitting

Send four things to **`<nicolas[point]gaudenzio[et]inserm[point].fr>`**`):

- [ ] The notebook, executed, **with outputs visible** (`File > Download > .ipynb`)
- [ ] The cluster annotation table from Part 6
- [ ] The one-page summary from Part 8
- [ ] Five to eight slides for a 15 minute presentation (Part 9), any format

Then we will schedule a **30 minute conversation**. We will pick three or four of your choices and
ask you to justify them, and we will ask what you would do differently with a
month instead of a short deadline. Come ready to disagree with us.

---

## Repository contents

| File | |
|---|---|
| `scRNAseq_case_study_R_and_Python.ipynb` | The case study. Both tracks in one notebook. |
| `README.md` | This file. |

The data is hosted separately and downloads itself from the first cell. Direct
links, if you need them:

- R: `https://web-genobioinfo.toulouse.inrae.fr/~rekren/case_data.RDS` (~23 MB)
- Python: `https://web-genobioinfo.toulouse.inrae.fr/~rekren/case_data.h5ad` (~38 MB)

---

## Troubleshooting

**If Colab does not offer an R runtime.** Start a Python runtime instead, run the
`rpy2` fallback cell at the end of Part 0 in Section 1, then prefix every R cell
with `%%R`. Size figures explicitly, for example `%%R -w 900 -h 420 -r 100`.

**The download fails.** Fetch the file in a browser from the link above and
upload it via the left sidebar (**Files > Upload**), then rerun the cell. It
picks the file up automatically.

**Setup is slow.** Two to four minutes for the Python track, three to six for R,
on a fresh runtime. The R setup installs `Seurat` from precompiled binaries; if
it starts compiling from source, the mirror did not resolve, so interrupt and
rerun the cell. Nothing in either track needs Bioconductor, so if you see a
package being fetched from `bioconductor.org`, something has gone wrong.

**The session disconnected and I lost everything.** Colab reclaims idle runtimes.
Save to Drive often, and rerun from the top; nothing takes more than a few
minutes.

**I submitted a notebook with the outputs cleared.** The single most common
mistake. Check before sending that your plots and printed tables are visible in
the downloaded file.

---

## Questions

Ask. Getting stuck on infrastructure is not part of the assessment, and telling
us early costs you nothing. Questions about *how to interpret* the data are a
different matter, and we would rather you wrote down your reasoning and your
uncertainty than waited for us to resolve it.
