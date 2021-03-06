# Introduction

Dobby is a CLI for developers used to automate common tasks workflows. Things like transitioning issues, creating and merging branches, creating pull requests, bumping versions, tagging... anything that is a repetitive, time consuming task in your development cycle, this tool is made to speed up.

## How it Works

Basically you create a file called `dobby.toml` in your project directory which defines some workflows. The format of this file is described in [the chapter on config][config], the key piece to which is the `workflows` array. For a full example of a `dobby.toml`, check out the file for this project!

Once you've got a config set up, you just run this program (`dobby` if you installed normally via cargo). That will prompt you to select one of your configured workflows. Do that and you're off to the races!

## Features

More detail on everything this program can do can be found by digging into [config] but here's a rough (incomplete) summary:

1. Select issues from Jira or GitHub to work on, transition and create branches from them.
2. Do some basic git commands like switching branches or rebasing.
3. Bump the version of your project using semantic rules.
4. Bump your version AND generate a Changelog entry from conventional commits.
5. Do whatever you want by running arbitrary shell commands and substituting data from the project!

## Concepts

You define a [config] file named `dobby.toml` which has some metadata (e.g. Jira details) about your project, as well as a set of defined [workflows][workflow]. Each [workflow] consists of a series of [steps][step] that will execute in order, stopping if any step fails. [Steps][step] can affect the [state] of the workflow. Some [steps][step] require that the workflow be in a specific [state] before they will work.

[config]: config/config.md
[workflow]: config/workflow.md
[step]: config/step/step.md
[state]: state/state.md
