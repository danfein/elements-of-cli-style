# Updates

## Claude Code
```
❯ claude update
Current version: 2.1.119
Checking for updates to latest version...
Claude Code is up to date (2.1.119)
```

## Pihole (DNS ad-blocker)

```
$ pihole -up
[i] Checking for updates…
[i] Pi-hole Core: update available
[i] Web Interface: update available
[i] FTL: update available
[i] Pi-hole core files out of date, updating local repo.
[✓] Check for existing repository in /etc/.pihole
...
```

Pihole uses a single dash with a word flag.
Conventionally a single dash is used with one letter flags `-v`, and two dashes would be used for words `--up`


## Brew (macOS package manager)

```
❯ brew update
Already up-to-date.
```

```
❯ brew update
Updated 9 taps (tilt-dev/tap, cloudfoundry/tap, knative/client, homebrew/core, homebrew/cask, homebrew/bundle, homebrew/cask-fonts, vmware-tanzu/pinniped and vmware-tanzu/carvel).
==> New Formulae
ansible-language-server   httpyac                   localtunnel               werf
gops                      knative/client/kn@1.3     sophus
==> Updated Formulae
Updated 730 formulae.
==> Deleted Formulae
boost-python                       komposition                        szip
==> New Casks
banana-cake-pop           font-harano-aji           manymc                    todesk
descript                  gdevelop                  mixed-in-key-live         vivid
espanso                   keysafe                   neovide                   wpsoffice-cn
==> Updated Casks
Updated 434 casks.
```

```
❯ brew upgrade
==> Upgrading 13 outdated packages:
coreutils 9.0_1 -> 9.1
vmware-tanzu/carvel/imgpkg v0.27.0 -> v0.28.0
go 1.18 -> 1.18.1
...
==> Downloading https://github.com/tilt-dev/tilt/releases/download/v0.27.2/tilt.0.27.2.mac.x86_64.tar.gz
==> Downloading from https://objects.githubusercontent.com/github-production-release-asset-2e65be/143896
######################################################################## 100.0%
...
==> Upgrading starship
  1.5.4 -> 1.6.2

==> Pouring starship--1.6.2.monterey.bottle.tar.gz
==> Caveats
zsh completions have been installed to:
  /usr/local/share/zsh/site-functions
==> Summary
🍺  /usr/local/Cellar/starship/1.6.2: 11 files, 6.2MB
==> Running `brew cleanup starship`...
Removing: /usr/local/Cellar/starship/1.5.4... (10 files, 5.8MB)
...

```

Feedback given when running an update / upgrade

## Google Cloud CLI

```
Your current Google Cloud CLI version is: 519.0.0
The latest available version is: 519.0.0

┌─────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
│                                                    Components                                                   │
├───────────────┬──────────────────────────────────────────────────────┬──────────────────────────────┬───────────┤
│     Status    │                         Name                         │              ID              │    Size   │
├───────────────┼──────────────────────────────────────────────────────┼──────────────────────────────┼───────────┤
│ Not Installed │ App Engine Go Extensions                             │ app-engine-go                │   4.5 MiB │
│ Not Installed │ Appctl                                               │ appctl                       │  18.5 MiB │
│ Not Installed │ Artifact Registry Go Module Package Helper           │ package-go-module            │   < 1 MiB │
│ Not Installed │ Cloud Bigtable Command Line Tool                     │ cbt                          │  18.5 MiB │
│ Not Installed │ Cloud Bigtable Emulator                              │ bigtable                     │   7.4 MiB │
│ Not Installed │ Cloud Datastore Emulator                             │ cloud-datastore-emulator     │  36.2 MiB │
│ Not Installed │ Cloud Firestore Emulator                             │ cloud-firestore-emulator     │  46.9 MiB │
│ Not Installed │ Cloud Pub/Sub Emulator                               │ pubsub-emulator              │  62.4 MiB │
│ Not Installed │ Cloud Run Proxy                                      │ cloud-run-proxy              │  11.3 MiB │
│ Not Installed │ Cloud SQL Proxy v2                                   │ cloud-sql-proxy              │  14.2 MiB │
│ Not Installed │ Google Container Registry's Docker credential helper │ docker-credential-gcr        │           │
│ Not Installed │ Kustomize                                            │ kustomize                    │   7.4 MiB │
│ Not Installed │ Log Streaming                                        │ log-streaming                │  16.0 MiB │
│ Not Installed │ Managed Flink Client                                 │ managed-flink-client         │ 383.4 MiB │
│ Not Installed │ Minikube                                             │ minikube                     │  43.5 MiB │
│ Not Installed │ Nomos CLI                                            │ nomos                        │  33.5 MiB │
│ Not Installed │ On-Demand Scanning API extraction helper             │ local-extract                │  22.4 MiB │
│ Not Installed │ Skaffold                                             │ skaffold                     │  33.3 MiB │
│ Not Installed │ Terraform Tools                                      │ terraform-tools              │  64.0 MiB │
│ Not Installed │ anthos-auth                                          │ anthos-auth                  │  20.9 MiB │
│ Not Installed │ config-connector                                     │ config-connector             │  88.7 MiB │
│ Not Installed │ enterprise-certificate-proxy                         │ enterprise-certificate-proxy │   7.6 MiB │
│ Not Installed │ gcloud Alpha Commands                                │ alpha                        │   < 1 MiB │
│ Not Installed │ gcloud Beta Commands                                 │ beta                         │   < 1 MiB │
│ Not Installed │ gcloud app Java Extensions                           │ app-engine-java              │ 128.3 MiB │
│ Not Installed │ gcloud app Python Extensions                         │ app-engine-python            │   3.8 MiB │
│ Not Installed │ gcloud app Python Extensions (Extra Libraries)       │ app-engine-python-extras     │   < 1 MiB │
│ Not Installed │ gke-gcloud-auth-plugin                               │ gke-gcloud-auth-plugin       │   3.3 MiB │
│ Not Installed │ istioctl                                             │ istioctl                     │  23.9 MiB │
│ Not Installed │ kpt                                                  │ kpt                          │  14.4 MiB │
│ Not Installed │ kubectl                                              │ kubectl                      │   < 1 MiB │
│ Not Installed │ kubectl-oidc                                         │ kubectl-oidc                 │  20.9 MiB │
│ Not Installed │ pkg                                                  │ pkg                          │           │
│ Installed     │ BigQuery Command Line Tool                           │ bq                           │   1.8 MiB │
│ Installed     │ Cloud Storage Command Line Tool                      │ gsutil                       │  11.8 MiB │
│ Installed     │ Google Cloud CLI Core Libraries                      │ core                         │  21.4 MiB │
│ Installed     │ Google Cloud CRC32C Hash Tool                        │ gcloud-crc32c                │   1.3 MiB │
└───────────────┴──────────────────────────────────────────────────────┴──────────────────────────────┴───────────┘
To install or remove components at your current SDK version [519.0.0], run:
  $ gcloud components install COMPONENT_ID
  $ gcloud components remove COMPONENT_ID

To update your SDK installation to the latest version [519.0.0], run:
  $ gcloud components update


Modify profile to update your $PATH and enable shell command completion?
```

## oh my zsh

```
➜  ~ omz update
Updating Oh My Zsh
         __                                     __
  ____  / /_     ____ ___  __  __   ____  _____/ /_
 / __ \/ __ \   / __ `__ \/ / / /  /_  / / ___/ __ \
/ /_/ / / / /  / / / / / / /_/ /    / /_(__  ) / / /
\____/_/ /_/  /_/ /_/ /_/\__, /    /___/____/_/ /_/
                        /____/

Oh My Zsh is already at the latest version.

To keep up with the latest news and updates, follow us on X: @ohmyzsh
Want to get involved in the community? Join our Discord: Discord server
Get your Oh My Zsh swag at: Planet Argon Shop
➜  ~
```