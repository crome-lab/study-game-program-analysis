# Data

Nothing in this folder is committed. `.gitignore` keeps both subfolders out of version control.

## data/raw

Notebook 01 looks for these Qualtrics and NVivo exports. It finds each file by key words, so small differences in the file name are fine.

| Contents | Key words in the file name |
|---|---|
| Child survey, first administration | `5-12` and `Pre` |
| Child survey, second administration | `5-12` and `Post` |
| Adolescent and adult survey, first administration | `13` and `Pre` |
| Adolescent and adult survey, second administration | `13` and `Post` |
| Advisory board demographics | `Advisory` and `Demographic` |
| Participant interview codebook | `Codebook` and `Post-survey` |
| Advisory board interview codebook | `Codebook` and `1-on-1` |
| Advisory board meeting codebook | `Codebook` and `Meeting` |

The survey files are standard Qualtrics exports (.xlsx) with the data on the first sheet, `Sheet0`.

## data/processed

Written by notebook 01 and read by notebook 02. These files carry a study ID instead of a name and keep only the fields the analysis uses. They are still record-level participant data, so they stay on institutional storage and are not shared publicly.
