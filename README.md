# Is harness engineering dead for big models?

An animated, single-page study of what a harness (the program around a language model: prompts, tools, memory, checks, retries) still decides when the model is a frontier one.

**Read it: https://gsalucci.github.io/harness-engineering-2026/**

What is in it:

- 874 papers fetched between 1 March and 17 November 2026, 870 read in full
- 4,267 claims and 4,378 designs, each with a word-for-word quote from its paper
- 334 harness ideas judged one topic at a time: where the harness is dead for big models, where it is alive, and why
- design patterns from the papers, a guide to design a harness for your case, and what the harness still decides about cost

## The data

The tables behind the page are in [`data/`](data/): papers, claims, designs, design patterns and ideas, as tab-separated files. [`data/README.md`](data/README.md) describes every column.

## How it was made, and its limits

The papers were read, the claims extracted and the verdicts judged by language models; a script checked that each quote exists in its paper (about 97 percent found). Whether a quote supports the claim attached to it was not checked, and no person re-read the tables. Authors mostly score their own systems. The last section of the page lists every limit; read it before quoting a number.

The page is one file, `index.html`. It loads the GSAP animation library from cdnjs and its fonts from Google Fonts, and nothing else.

## Licence

Text and data: [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/). Quoted sentences belong to the authors of the papers they come from.
