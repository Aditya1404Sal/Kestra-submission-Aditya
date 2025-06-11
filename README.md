# 📣 Automatic "What's New" Documentation Generator

## Overview

This Kestra flow automates the generation of a `What's New` section in your open source project's documentation by:

- Fetching new commits made to the `main` branch each day
- Summarizing the commit log using OpenAI
- Updating and pushing the summary to `docs/whats-new.md` on the same branch

## Why This Flow?

Maintainers often forget or delay updating documentation with recent changes. This leads to outdated docs and confusion for new users and contributors. With this flow:

- Docs are kept fresh automatically
- Non-developers can track progress via human-readable summaries
- Contributors feel recognized as their changes are reflected daily

## Use Case

- OSS projects with frequent small changes (e.g., WasmCloud, Fermyon Spin, CLI tools)
- Teams that want changelogs without manually formatting every commit
- Community-driven projects aiming for transparency

## What It Does

1. **Clones the main repo**
2. **Fetches commits from the past day**
3. **Feeds commit log to OpenAI to generate a natural language summary**
4. **Updates `docs/whats-new.md`** 
5. **Commits and pushes the new content**

## Secrets Needed

Set the following in Kestra’s Secrets UI:

- `GITHUB_TOKEN`: GitHub token with write access
- `OPENAI_API_KEY`: OpenAI API key (GPT-4 is recommended)

## Schedule

Runs every day at 9 AM UTC.

## Maintainer

Built by Adi for [Kestra Hackweek by WeMakeDevs](https://wemakedevs.org/). 
Feel free to fork or extend this flow for Slack/Notion publishing or to support multiple branches.
