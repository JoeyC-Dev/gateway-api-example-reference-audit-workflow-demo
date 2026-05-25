# Gateway API Example Reference Audit Workflow Demo

This repository is a demo for validating example YAML reference headers with
GitHub Actions. It is intended for testing and demonstrating the reference-check
workflow, not for serving as the upstream Gateway API repository.

The demo adds a workflow that checks whether example YAML files under
`examples/` have reference headers that match their real usage from
documentation files under `site/content/en/` and `geps/`.


## What it does

- Detect changed example YAML and Markdown files in pull requests.
- Verify `#$` reference headers in example YAML files.
- Report missing, stale, duplicated, and unreferenced example YAML references.
- Write the verification report to the GitHub Actions job summary.

## Note

- The check is skipped when neither example YAML files nor reference Markdown
  files are changed.
- If only files under `examples/` are changed, only the changed example YAML
  files are checked.
- If any Markdown file is changed, the full example YAML check runs.
- Unreferenced example YAML files are reported but do not fail the check.

## Original Project

For the official Kubernetes Gateway API project, see:
https://github.com/kubernetes-sigs/gateway-api
