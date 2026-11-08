# nlp-03-text-exploration-context

[![Python 3.14](https://img.shields.io/badge/python-3.14%2B-blue?logo=python)](pyproject.toml)
[![CI](https://github.com/ajaneh/nlp-03-text-exploration-context/actions/workflows/ci-python-zensical.yml/badge.svg)](https://github.com/ajaneh/nlp-03-text-exploration-context/actions/workflows/ci-python-zensical.yml)

[![uv managed](https://img.shields.io/badge/uv-managed-DE5FE9)](https://docs.astral.sh/uv/)
[![ty type checked](https://img.shields.io/badge/ty-type_checked-2F80ED)](https://docs.astral.sh/ty/)
[![Zensical docs](https://img.shields.io/badge/Zensical-docs-purple)](https://zensical.org/)
[![MIT](https://img.shields.io/badge/license-MIT-yellow.svg)](LICENSE)

> Explore a labeled text corpus using token frequencies, category comparisons, and contextual patterns.

## Project Overview

Author: Alex Heyert

Date: 2026-11

This project explores a TODO:
 small, labeled text corpus with Python and Polars.

It examines vocabulary patterns, compares document categories,
and explores word relationships through co-occurrence and bigrams.

These techniques provide foundations for understanding
more advanced NLP methods, including
language representations and embeddings.

The project is configured in
[pyproject.toml](pyproject.toml).

## Data

I used ChatGPT to create a CSV corpus of incoming job-related emails from two linked Gmail inboxes, searching messages dated September 1, 2025, through November 8, 2026. The CSV contains 202 messages which are categorized as:
- application acknowledgements
- rejections
- interview invitations
- process updates
- job offers.
ChatGPT removed detected personal names and contact details while retaining company names. This curated corpus is not a complete application history or a count of unique jobs. The datafile is not committed to protect privacy. I realize it's ironic that ChatGPT used NLP to categorize the email message text, but classification is not the goal.

## Approach

The project uses Python and Polars to explore patterns in job correspondence. Most rejection emails sound the same, so I'm exploring how similar (or different) the email language is.

The example demonstrates:

- Representing a collection of documents as a corpus.
- Tokenizing and cleaning text.
- Computing global token frequencies.
- Comparing token frequencies across categories.
- Identifying frequently occurring words within categories.
- Examining word co-occurrence using context windows.
- Creating and counting bigrams.
- Visualizing and interpreting token distributions.

Explore these important project components:

- [pyproject.toml](pyproject.toml) - project identity, dependencies, and tool configuration.
- [src/nlp/nlp_corpus_explore.py](src/nlp/nlp_corpus_explore.py) - executable Python corpus analysis.
- [tests/](tests/) - automated tests.
- [.github/workflows/](.github/workflows/) - automated testing and documentation deployment.
- [docs/](docs/) - project documentation.
- [zensical.toml](zensical.toml) - documentation configuration.

The goal is to observe structure in text
before applying machine learning or language models.

## Run the Project

Follow the [Professional Python Workflow Guide](https://denisecase.github.io/pro-analytics-02/)
to set up your machine and project environment.

From a VS Code terminal in the project root:

```shell
uv run python -m nlp.nlp_corpus_heyert
```

Close each visualization window after viewing
so the script can continue executing.

## Results

TODO

## Verification

Run the automated tests:

```shell
uv run python -m pytest
```

## Project Documentation

Project documentation is in the [docs/](docs/) directory and is built using Zensical.

Published documentation URL: TODO

## CI/CD and GitHub Actions

This project includes continuous integration and continuous deployment (CI/CD)
to check project files and publish the docs.

GitHub Actions include:

- [CI: Python and Documentation Checks](https://github.com/ajaneh/nlp-03-text-exploration-context/actions/workflows/ci-python-zensical.yml)
- [CD: Documentation Deployment](https://github.com/ajaneh/nlp-03-text-exploration-context/actions/workflows/deploy-zensical.yml)

## Developer Reference

Follow the
[Professional Python Workflow Guide](https://denisecase.github.io/pro-analytics-02/)
for **detailed instructions and troubleshooting**.

### Initialize and Update the Python Environment

With the project open in VS Code, open a VS Code terminal.
Paste each command and hit Enter or Return after to run it.

```shell
uvx pup-clean --delete
uv self update
uv python pin 3.14
uv python install
uv lock --upgrade
uv sync
uv audit
```

### Set Up and Run Git Hooks

Set up and run the git hooks to perform
basic checks automatically before
any changes get pushed to GitHub.

In the VS Code terminal,
paste each command and hit Enter or Return after to run it.

```shell
uvx prek install --force
uvx prek update --freeze --cooldown-days 7

git add -A
uvx prek run --all-files
# repeat if changes were made
uvx prek run --all-files
```

### Run Common Chores

Run linters, formatters, type checks, tests, and
build the documentation.

```shell
uv run ruff check . --fix
uv run ruff format .

uv run ty check
uv run python -m pytest
uv run python -m zensical build
```

### Git add-commit-push to GitHub

After making useful changes, save your work to GitHub.

```shell
git add -A
git commit -m "describe your changes in quotes"
git push -u origin main
```

## Developer Notes

- Use the **UP ARROW** and **DOWN ARROW** in the terminal to scroll through past commands.
- Use `CTRL+f` to find (and replace) text within a file.

## Developer Tools

This project uses professional Python tools to support development,
testing, documentation, and code quality.

- [uv](https://docs.astral.sh/uv/) - Python environments and dependencies.
- [Ruff](https://docs.astral.sh/ruff/) - Python linting and formatting, configured in [.ruff.toml](.ruff.toml).
- [ty](https://docs.astral.sh/ty/) - Python type checking.
- [pytest](https://docs.pytest.org/) - automated Python testing, configured in [.pytest.toml](.pytest.toml).
- [prek](https://prek.j178.dev/) - Git hooks and automated checks, configured in [prek.toml](prek.toml).
- [Zensical](https://zensical.org/) - project documentation, configured in [zensical.toml](zensical.toml).

## Links

- [Documentation source](docs/)
- [GitHub Repository](https://github.com/ajaneh/nlp-03-text-exploration-context)
- [Professional Python Workflow Guide](https://denisecase.github.io/pro-analytics-02/)
- [Citation](CITATION.cff)
- [License](LICENSE)
