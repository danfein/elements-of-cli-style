# Elements of cli style

A working reference for CLI design: real terminal output from many CLIs, organized by UX pattern (confirmation, errors, progress, tables, ...) so a pattern can be looked up and compared across tools without needing a live session with each one.

## Patterns
*  [Alerts](alerts.md) — notices/warnings surfaced during unrelated operations (gcloud component updates, brew uninstall warnings, krew plugin caveats)
*  [Confirmation](confirmation.md) — y/n and destructive-action prompts (ollama, Claude Code install, pyenv uninstall, `cf create-space`, gcloud update)
*  [Context setting](context.md) — interactive org/space/project/context selection and switching (`cf login`/`target`, `tanzu login`/`context`, kubectx)
*  [Delete](delete.md) — confirmation wording across resource types and CLIs (`cf delete-space`/`delete-org`/`delete`/`delete-route`/`delete-service`)
*  [Errors](errors.md) — did-you-mean suggestions and error message structure (cf typo correction, go install)
*  [Help text](help.md) — `--help`/top-level usage output across CLIs (pihole, om, cf, oc, kubectl, snowflake)
*  [Lists](lists.md) — structured list/detail rendering (`tanzu profile get`)
*  [Manual pages](man.md) — *stub*
*  [Progress indicators](progress.md) — install/long-running-operation feedback (Claude Code, ollama, git clone, `tanzu plugin install`)
*  [Prompts](prompts.md) — interactive Y/N and multiple-choice prompts (brew, oh-my-zsh, gcloud, tanzu, `gh auth login`)
*  [Status](status.md) — current-state output (`pihole status`, `git status`)
*  [Tables](tables.md) — structured key:value and nested detail views (`tanzu app get`)
*  [Troubleshooting](troubleshooting.md) — diagnostic output (`brew doctor`)
*  [Updates](update.md) — self-update/upgrade command output (claude, pihole, brew, gcloud)
*  [Configuration](configuration.md) — persistent CLI config flags (`cf config --locale`, `--trace`)
*  [CLI accessibility](cli-accessibility.md) — screen-reader/plaintext accommodations (gcloud accessibility mode)
*  [Authentication](auth.md) — login/auth flows across CLIs (npm, `cf api`/`login`/`--sso`, Tanzu Hub login)
*  [kf CLI](kf.md) — full command reference for `kf`, a cf-like CLI for apps on Kubernetes
*  [Resources and reference](resources.md) — external CLI design guidance and writing style guides (CLIG, Atlassian, Heroku, gov style guides)

## Installation
*  [Claude Code](Installation/claudecode.md)
*  [gcloud](Installation/gcloud.md)
*  [OpenShift CLI (oc)](Installation/openshift.md)

## CLI reference libraries
Per-command output reference for specific CLIs, organized as their own directories rather than by pattern — used when designing against one of these tools specifically.
*  [Cloud Foundry cf CLI (classic)](cloud-foundry/README.md) — single-foundation OSS Cloud Foundry
*  [Tanzu Platform for Cloud Foundry cf CLI](tanzu-cf-cli/README.md) — `cf` via Tanzu Hub (multi-foundation, org group/space group)
*  [Tanzu CLI](tanzu/tanzu-cli.md) / [styleguide](tanzu/tanzu-cli-styleguide.md)
*  [Tanzu Data Management Console (tdmc)](tanzu/tdmc.md)
*  [App accelerators](tanzu/app-accerators.md) — *stub*
*  [VCF install](vcf/install-vcf.md) — *empty*
