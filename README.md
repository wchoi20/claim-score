# claim-score

This is a repository for relevant files used in 'claim-score' project.

The folder 'original-data'includes original data of MegaWika (Barham et al, 2023). Only necessary rows from the dataset are extracted (passage, question, answer, score) and are used.

## MegaWika-{train/test}-filtered.csv

These are two csv files that are a filtered version of the original MegaWika. Filtering represents removing data that have been marked nonsense or not-supported by the annotators (which is labeled in the original MegaWika).

## MegaWika-{train/test}-filtered-declarative-{v1/v2}.csv

These are four csv files that are a declarative version of the QA pairs in MegaWika. Conversion of QA pairs into declarative sentences were made by a fine-tuned FLAN-T5-base using QA2D dataset (Demszky et al, 2018). In QA2D dataset, there are two versions of declaratives: turker_answer (v1) and rule-based (v2). I trained two separate FLAN-T5 using two versions of declaratives and found that a model trained with turker_answer produces better output. Not all conversion instances were different but in such cases, v1 produced a sentence more similar to the natural language.

## MegaWika-train-declarative-difference.csv

This csv file displays two different versions of QA pairs to declarative conversion. v1 represents a sentence produced using turker_answer based model and v2 represents that using rule-based based model.


## Examples

These are some examples of the difference between two conversion models:

Q: for which parliamentary constituency did don primarolo serve from 1987 to 2015
A: Bristol South
turker_answer based (v1): Don primarolo served Bristol South from 1987 to 2015.
rule-based based (v2): Don primarolo served Bristol South from 1987 to 2015 from Bristol South.

Q: how many new bank notes are there in india
A: 100
turker_answer based (v1): There are 100 new bank notes in India.
rule-based based (v2): There in India are 100 new bank notes.

## 

Thus, for further steps in this project, I plan to use declarative sentences converted using turker_answer based model (v1).
