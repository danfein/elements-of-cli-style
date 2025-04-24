# Gcloud CLI installation

Docs: https://cloud.google.com/sdk/docs/install  

```
➜  google-cloud-sdk ./install.sh
Welcome to the Google Cloud CLI!

To help improve the quality of this product, we collect anonymized usage data
and anonymized stacktraces when crashes are encountered; additional information
is available at <https://cloud.google.com/sdk/usage-statistics>. This data is
handled in accordance with our privacy policy
<https://cloud.google.com/terms/cloud-privacy-notice>. You may choose to opt in this
collection now (by choosing 'Y' at the below prompt), or at any time in the
future by running the following command:

    gcloud config set disable_usage_reporting false

Do you want to help improve the Google Cloud CLI (y/N)?


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

Do you want to continue (Y/n)?

The Google Cloud SDK installer will now prompt you to update an rc file to bring the Google Cloud CLIs into your environment.

Enter a path to an rc file to update, or leave blank to use [/Users/danielfein/.zshrc]:
Backing up [/Users/danielfein/.zshrc] to [/Users/danielfein/.zshrc.backup].
[/Users/danielfein/.zshrc] has been updated.

==> Start a new shell for the changes to take effect.


Google Cloud CLI works best with Python 3.12 and certain modules.

Download and run Python 3.12 installer? (Y/n)?

Running Python 3.12 installer, you may be prompted for sudo password...
Password:
installer: Package name is Python
installer: Installing at base path /
installer: The install was successful.
Setting up virtual environment
Creating virtualenv...
Installing modules...
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 5.5/5.5 MB 1.3 MB/s eta 0:00:00
  Installing build dependencies ... done
  Getting requirements to build wheel ... done
  Preparing metadata (pyproject.toml) ... done
   ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 11.3/11.3 MB 45.7 MB/s eta 0:00:00
  Building wheel for crcmod (pyproject.toml) ... done
Virtual env enabled.

For more information on how to get started, please visit:
  https://cloud.google.com/sdk/docs/quickstarts

...