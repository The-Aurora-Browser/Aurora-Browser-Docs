# GitHub Wiki Template

Repository template to manage a GitHub wiki that is synchronized with a GitHub project.\
This wiki is synchronized with the [project-repo-template](https://github.com/mhatzl/project-repo-template).

The structure is loosely related to the [arc42 documentation](https://docs.arc42.org/home/).\
To create system views, you should take a look at [C4](https://c4model.com/), and the related [Structurizr DSL](https://structurizr.com/).

This template is tailored to GitHub repositories, but the core concepts work for any project using a version control system.

**Steps to adapt this template.**

1. Add the wiki repository of your project repository as additional remote (checkout the [sync-wiki action](/.github/workflows/sync-wiki.yml) for more information)
1. Change the link in [sync-wiki action](/.github/workflows/sync-wiki.yml) to point to your remote project wiki
1. Adapt the Definition of Done in the [pull request template](/.github/pull_request_template.md)
1. Optional: Adapt the license to be in sync with the license of your project
1. Adapt the existing markdown pages (see [template placeholders](#template-placeholders) for more details)

## Wiki Pages

GitHub wiki only considers files, and ignores any hierarchy set via folders.
This enforces that every filename must be unique in the entire wiki.

This template is structured in a way to group related files, and enforce an order to first show more important pages on the wiki.

## Template Placeholders

In this template, many sections include placeholder text to provide some guidance of what the section should be about.
These placeholders are inside `{{ }}` blocks.

Some sections also include example content that is given inside `[[ ]]` blocks.

## Synchronize Repository and Wiki

Every GitHub wiki has its own git repository, with the link to it shown on the sidebar of the wiki.
This setup allows edits directly in the wiki section of a project, but makes it hard to encourage external contributions, because the common PR workflow is not available.\
Therefore, this template should be placed in its own repository, and synchronize changes to the internal repository of the project wiki.
Since the wiki is shown in the project repository, issues should still be handled in the project repository, because users would expect this.
To enforce this, the *issue* tab is deactivated in this template. More precisely, every feature except PRs was disabled, to make it clear that everything except PRs should be handled in the project repository.

## GitHub Actions

This template contains the following GitHub actions:

- `sync_wiki` ... Automatically pushes changes to the wiki repository of the associated project

## GitHub Issue/PR Labels

Repositories created by GitHub templates do not adopt the issue/PR labels set in the template.
Instead, each one must be copied manually, which is unfortunate, but must only be done once.

**Below are the [labels](https://github.com/mhatzl/wiki-repo-template/labels) defined in the wiki template:**

- `blocked` ... Marks this PR that it is blocked by another issue/PR (Color: `#F83A55`)
- `declined` ... This PR was declined (Color: `#ffffff`)
- `waiting-on-assignee` ... PR author or reviewer is awaiting response from assignee (Color: `#FEF2C0`)
- `waiting-on-author` ... Assignee or reviewer is awaiting response from PR author (Color: `#463F12`)
- `waiting-on-reviewer` ... Author or assignee is awaiting response from reviewer (Color: `#E6A2AE`)

## GitHub Settings

Repository settings are not adopted from templates, and must be set manually.
Below are the recommended settings that work well with this wiki template.

**General Settings:**

- **Disable** all features to only allow pull requests
- Only allow squash merging for pull requests
- Automatically delete head branches

# License

MIT Licensed
