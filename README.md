# Law Agent Evaluation Dataset

Supplementary evaluation data for the master's thesis:

**Mitmekeelse RAG-põhise õigusassistendi arendamine Eesti kehtiva õiguse päringutele vastamiseks**

**Author:** Dmitri Derevjanko  
**University:** Tallinn University of Technology (TalTech)  

## Overview

This repository contains an evaluation dataset for Law Agent, a multilingual legal assistant that uses Retrieval-Augmented Generation (RAG) to answer questions using Estonian legislation published in Riigi Teataja.

The dataset preserves the evaluation questions, generated answers, retrieved legal excerpts, source references, and retrieval metrics independently of the project's live website.

## Dataset

File: `law_agent_evaluation_100_et.json`

The dataset contains 100 questions written in Estonian. Some questions explicitly request an answer in English or Russian.

The questions cover criminal, civil, administrative, labour, and tax law.

Each case includes:

- The question identifier, category, language, and text.
- The answer generated during the evaluation.
- The system's heuristic confidence rating.
- The requested legal reference date (`as_of_date`).
- Retrieved source excerpts, legal act titles, section references, validity dates, and source URLs.
- Reference sections and per-question retrieval metrics.

The file also contains aggregate evaluation results.

## Evaluation Results

| Metric | Value |
| --- | ---: |
| Questions | 100 |
| Successfully processed queries | 100 |
| Hit@1 | 78.00% |
| Precision@5 | 20.20% |
| Recall@5 | 90.67% |
| MRR@5 | 0.8412 |

Retrieval metrics compare the first five unique retrieved section references with the reference sections assigned to each question. Aggregate scores are averaged across questions.

These metrics describe retrieval performance. Successful query processing and the presence of citations do not establish that an answer is legally correct or complete.


## Limitations

- Reference sections were selected and checked by the thesis author.
- The answers were not independently evaluated by legal experts.
- Relevant legal provisions may be missing from the retrieved context.
- An answer may cite retrieved sources while remaining incomplete or making an unsupported generalisation.
- Confidence ratings are internal heuristics, not probabilities of legal correctness.
- This dataset evaluates Estonian input questions; it does not separately establish retrieval quality for English or Russian input questions.

The answers are preserved as generated, including errors and incomplete responses.

## Viewing the Data

Download or open the JSON file to inspect the evaluation records.

An interactive presentation is available at:

https://counsel.dmitriderevjanko.com/benchmark

The JSON file in this repository is the preserved supplementary dataset. The interactive website may change over time.

## Intended Use

This dataset supports inspection of the thesis results and further research into retrieval and citation behaviour in legal RAG systems.

It is provided for research and educational purposes. Generated answers should not be treated as legal advice.
