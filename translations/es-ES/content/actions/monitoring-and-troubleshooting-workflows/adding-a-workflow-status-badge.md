---
title: Agregar una insignia de estado de flujo de trabajo
intro: Puedes mostrar una insignia de estado en tu repositorio para indicar el estado de tus flujos de trabajo.
redirect_from:
  - /actions/managing-workflow-runs/adding-a-workflow-status-badge
versions:
  fpt: '*'
  ghes: '*'
  ghae: '*'
  ghec: '*'
shortTitle: Agregar una insignia de estado
---

{% data reusables.actions.enterprise-beta %}
{% data reusables.actions.enterprise-github-hosted-runners %}

{% note %}

**Note**: Workflow badges in a private repository are not accessible externally, so you won't be able to embed them or link to them from an external site.

{% endnote %}

{% data reusables.repositories.actions-workflow-status-badge-intro %}


To add a workflow status badge to your `README.md` file, first find the URL for the status badge you would like to display. Then you can use Markdown to display the badge as an image in your `README.md` file. For more information about image markup in Markdown, see "[Basic writing and formatting syntax](/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#images)."

## Usar el nombre de archivo del flujo de trabajo

You can build the URL for a workflow status badge using the name of the workflow file:

```
{% ifversion fpt or ghec %}https://github.com{% else %}<HOSTNAME>{% endif %}/<OWNER>/<REPOSITORY>/actions/workflows/<WORKFLOW_FILE>/badge.svg
```

To display the workflow status badge in your `README.md` file, use the Markdown markup for embedding images. For more information about image markup in Markdown, see "[Basic writing and formatting syntax](/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax#images)."

For example, add the following Markdown to your `README.md` file to add a status badge for a workflow with the file path `.github/workflows/main.yml`. El `OWNER` del repositorio es la organización `github` y el nombre del `REPOSITORY` es `docs`.

```markdown
![flujo de trabajo de ejemplo](https://github.com/github/docs/actions/workflows/main.yml/badge.svg)
```

## Utilizar el parámetro `branch`

To display the status of a workflow run for a specific branch, add `?branch=<BRANCH_NAME>` to the end of the status badge URL.

For example, add the following Markdown to your `README.md` file to display a status badge for a branch with the name `feature-1`.

```markdown
![example branch parameter](https://github.com/github/docs/actions/workflows/main.yml/badge.svg?branch=feature-1)
```

## Utilizar el parámetro `event`

To display the status of workflow runs triggered by the `push` event, add `?event=push` to the end of the status badge URL.

For example, add the following Markdown to your `README.md` file to display a badge with the status of workflow runs triggered by the `push` event, which will show the status of the build for the current state of that branch.

```markdown
![example event parameter](https://github.com/github/docs/actions/workflows/main.yml/badge.svg?event=push)
```
