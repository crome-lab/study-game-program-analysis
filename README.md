# GAME program: survey analysis

Analysis code for the manuscript *Dance is Medicine: A Mixed Methods Pilot Study Using Gospel Afrobeat to Promote Physical Activity*.

GAME is an 8-week, family-based dance program built around Gospel and Afrobeats music, delivered at three community sites in South-Central Wisconsin between April 2024 and March 2025. This repository holds the code behind the quantitative results: participant characteristics, the participant flow, and the paired survey comparisons shown in the manuscript's tables and figures.

Citation details will be added once the article is published.

## What is in here

```
notebooks/
  01_prepare_data.ipynb   links each person's two surveys and writes de-identified files
  02_analysis.ipynb       produces every table and figure from the de-identified files
data/
  raw/                    raw survey exports go here (not included, see below)
  processed/              de-identified files written by notebook 01 (not included)
results/
  figures/                Figures 1 to 3
  tables/game_results.xlsx
```

Both notebooks are saved with their outputs, so the results can be read without running anything.

## Data

The participant data are not included. The surveys were completed by adults and by parents on behalf of children in a small community sample, and even without names the combination of site, age, household income and race could identify people. De-identified data are available from the corresponding author on reasonable request, subject to approval by the institutional review board.

`data/README.md` lists the files notebook 01 expects.

## Running the analysis

Python 3.11 or later.

```bash
python -m venv .venv
source .venv/bin/activate        # on Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Put the raw exports in `data/raw/`, then run `notebooks/01_prepare_data.ipynb` followed by `notebooks/02_analysis.ipynb`. Notebook 01 is the only step that sees participant names; it stops with an error if any name turns up in its output.

## Where each result comes from

| Manuscript | Notebook 02 section | Sheet in `game_results.xlsx` |
|---|---|---|
| Table 1, participant characteristics | Table 1 | `Table1_characteristics` |
| Figure 1, participant flow | Figure 1 | `Participant_flow` |
| Figure 2, linked adult respondents | Paired results | `Figure2_linked_adults` |
| Figure 3, linked child respondents | Paired results | `Figure3_linked_children` |
| Supplemental Table 1, advisory board | Supplemental Table 1 | `SuppTable1_advisory_board` |
| Supplemental Table 2, response distributions | Supplemental Table 2 | `SuppTable2_distributions` |
| Survey intervals and sensitivity checks | Time between the two surveys, Without advisory board members, Answers that flip | `Survey_intervals`, `Sensitivity_no_board`, `Sensitivity_no_flips` |

## Analysis notes

- **Descriptive only.** No inferential tests are run. A single-arm design cannot support causal inference and the sample is too small to estimate effects with useful precision.
- **First and second administration.** Every survey item says that GAME has already helped (for example, "Participating in the GAME classes has improved my sleep"), and the program ran on a rolling basis, so the two surveys are not treated as a baseline and a follow-up.
- **Linking the two surveys.** A second survey is linked to the same person's first survey by name, allowing for first-name versus full-name entries, accents and small spelling differences, with age, gender and race used to confirm name variants.
- **Denominators.** For each item, a pair counts only if the person answered that item on both surveys. "Not applicable" is treated as an answer and stays in the denominator.
- **Race and ethnicity.** The question allowed more than one answer; anyone who chose several is counted under the first.
- **Advisory board members.** Some board members, including instructors, also completed participant surveys. They are included in the main results, and notebook 02 shows the results without them.

## Ethics and funding

The study was approved by the University of Wisconsin-Madison Institutional Review Board. It was supported by a Clinical and Community Outcomes Research (CCOR) Pilot Award from the University of Wisconsin Institute for Clinical and Translational Research (ICTR), funded by the Wisconsin Partnership Program through a Strategic Infrastructure grant to ICTR.

## License

The code is released under the MIT License. The license does not cover participant data.
