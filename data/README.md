# Data behind "Is harness engineering dead for big models?"

Five tab-separated files sit beside the page. They hold 874 papers; 4,267 measured claims and 4,378 designs, each with a word-for-word quote and a column saying whether a script found the quote in the paper; 539 design patterns grouped from the designs; and 334 ideas judged one topic at a time by a language model, each with the papers for and against and a status. Every file has one header row. Paper identifiers are arXiv numbers (for example 2603.05344) or start with `ext-` (sources outside arXiv).

## papers.tsv (874 rows)

- `identifier`: the paper's identifier.
- `published`: publication date.
- `title`: paper title.
- `kind`: core (the harness is what the paper designs or measures), side (the harness is only the setting) or off (not about agent harnesses).
- `type`: kind of paper, such as system, measurement-study, benchmark, security, position, survey, theory, dataset or other.
- `bare`: yes if the paper compares the same model with and without a harness, or across harnesses.
- `ladder`: yes if the paper tests several models of different strength.
- `small`: yes if the paper covers small or local models.
- `reliability`: yes if the paper measures repeatability or variance.
- `testing`: yes if the paper is about how to test harnesses.
- `trend`: how the paper says the harness gain moves as models get stronger: unstated, mixed, shrinks, grows or holds.
- `finding`: one-sentence summary of what the paper found.
- `depth`: how much of the paper was read: full or abstract.

## ideas.tsv (334 rows)

- `topic`: the topic the idea was judged under.
- `idea`: the idea, written as one sentence.
- `regime`: how often the bare model already finishes the task where the idea applies: out-of-reach (rarely), harness-decides (sometimes, so the harness decides the outcome), harness-polishes (mostly), all, or unclear. A few rows carry other labels.
- `papers_for`: papers that support it, each as identifier:date.
- `papers_against`: papers that argue against it, or none.
- `newest_evidence`: date of the newest paper cited.
- `models`: models named in the evidence.
- `best_evidence`: the strongest measured result, with its paper.
- `evidence_quality`: a rating (weak, medium) followed by the reason.
- `why`: the reason for the status.
- `status`: the verdict: survived, contested, stale, unmeasured or superseded.

## claims.tsv (4,267 rows)

- `identifier`: the paper the claim comes from.
- `published`: publication date of the paper.
- `topic`: topic of the claim.
- `claim`: the claim in one sentence.
- `direction`: harness-helps, harness-hurts, harness-no-effect or not-applicable.
- `measured`: measured, or argued without a measurement.
- `numbers`: the numbers the paper gives.
- `models`: models used.
- `tier`: model tier: frontier, mid, small, mixed or none.
- `tasks`: tasks or benchmarks used.
- `runs`: number of runs.
- `page`: page of the paper where the quote is.
- `quote`: the sentence from the paper that backs the claim.
- `quote_found`: yes if a script found the quote in the paper, no if not.

## designs.tsv (4,378 rows)

- `identifier`: the paper the design comes from.
- `published`: publication date of the paper, or unknown.
- `kind`: kind of design, such as control-loop, evaluation-method, verification, tools, self-improvement, context, memory or state-records.
- `name`: short name of the design.
- `what_and_how`: what the design does and how.
- `problem`: the problem it addresses.
- `where`: whether code, the model or both does the work.
- `evidence`: measured-against-baseline, measured-no-baseline or argued.
- `models_and_number`: models and the key number reported.
- `quote`: the sentence from the paper that backs the design.
- `quote_found`: yes if a script found the quote in the paper, no if not.

## patterns.tsv (539 rows)

- `kind`: group the pattern belongs to.
- `pattern`: name of the pattern.
- `what_and_how`: what the pattern does and how.
- `problem`: the problem it addresses.
- `where`: whether code, the model or both does the work.
- `papers`: identifiers of all papers that use it.
- `papers_measured`: identifiers of the papers that measured it.
- `models`: models named in the evidence.
- `best_number`: the strongest measured result, with its paper.
- `standing`: how common the pattern is: consensus, common, rare or outlier.
- `opposes`: another pattern it disagrees with, or none.
- `novelty`: known, or novel with a reason.
- `verdict`: the verdict (survived, contested, stale or not judged) with a reason.
- `recommendation`: a build or test advice line for a reader.
- `paper_count`: number of papers in `papers`.
- `measured_count`: number of papers in `papers_measured`.

## Limits

- Verdicts were judged by a language model, not by a person.
- Tables were built by models and no person re-read them.
- A quote being found shows the sentence exists, not that it supports the claim.
- Identifiers starting with `ext-` are sources outside arXiv.

## How the papers were collected

- arXiv: the public listing interface was searched over first-version dates from 1 March to 17 November 2026, in two-month windows, with these queries: "harness engineering"; "agent harness"; "agentic harness"; "coding agent" together with harness; "evaluation harness" together with agent; "model harness"; harness in the title together with agent or LLM in the abstract; "agent scaffold" or "agent scaffolding".
- A candidate was kept only if its title or abstract contains "harness" or "scaffold" and, judged by a language model from title and abstract, harnesses or scaffolds for language-model agents are a main subject. Other uses of the word (wiring, hardware test rigs) were dropped.
- 37 papers come from outside arXiv, found by web search (OpenReview, ACL Anthology, open-access items of the ACM Digital Library and IEEE Xplore, Semantic Scholar, Zenodo, SSRN, TechRxiv, technical reports), and only where a PDF was openly available.
- This is a keyword collection, not a complete census: a paper about agent harnesses that uses none of these words is missing. The exact query list differed slightly between date windows.

By Giancarmine Salucci. Last updated 24 November 2026. Licence: Creative Commons Attribution 4.0 International, https://creativecommons.org/licenses/by/4.0/. Quoted sentences belong to the authors of the papers they come from.
