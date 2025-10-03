# Confirmation

## Pyenv (python verison manager)

```
❯ pyenv uninstall 3.10.0
pyenv: remove /Users/dfein/.pyenv/versions/3.10.0? [y|N] y

```

Square brackets, vertical bar divider, default choice capitalized

## cf CLI space create
```
$ cf create-space example-two
Creating space example-two in org acme-fitness as daniel.fein@broadcom.com...
OK

Assigning role SpaceManager to user daniel.fein@broadcom.com in org acme-fitness / space example-two as daniel.fein@broadcom.com...
OK

Assigning role SpaceDeveloper to user daniel.fein@broadcom.com in org acme-fitness / space example-two as daniel.fein@broadcom.com...
OK

TIP: Use 'cf target -o "acme-fitness" -s "example-two"' to target new space
```

## Google Cloud Update
```
Beginning update. This process may take several minutes.


Your current Google Cloud CLI version is: 519.0.0
You will be upgraded to version: 541.0.0

┌─────────────────────────────────────────────────────────────────────────────┐
│                      These components will be updated.                      │
├─────────────────────────────────────────────────────┬────────────┬──────────┤
│                         Name                        │  Version   │   Size   │
├─────────────────────────────────────────────────────┼────────────┼──────────┤
│ BigQuery Command Line Tool                          │     2.1.24 │  1.8 MiB │
│ BigQuery Command Line Tool (Platform Specific)      │     2.1.17 │  < 1 MiB │
│ Cloud Storage Command Line Tool                     │       5.35 │ 12.4 MiB │
│ Cloud Storage Command Line Tool (Platform Specific) │       5.34 │  < 1 MiB │
│ Google Cloud CLI Core Libraries                     │ 2025.09.29 │ 22.6 MiB │
│ Google Cloud CLI Core Libraries (Platform Specific) │ 2025.05.23 │  < 1 MiB │
│ Google Cloud CRC32C Hash Tool (Platform Specific)   │      1.0.0 │  1.4 MiB │
└─────────────────────────────────────────────────────┴────────────┴──────────┘
┌────────────────────────────────────────────────────────────────────┐
│                These components will be installed.                 │
├─────────────────────────────────────────────┬────────────┬─────────┤
│                     Name                    │  Version   │   Size  │
├─────────────────────────────────────────────┼────────────┼─────────┤
│ gcloud cli dependencies (Platform Specific) │ 2021.04.16 │ < 1 MiB │
└─────────────────────────────────────────────┴────────────┴─────────┘

A lot has changed since your last upgrade.  For the latest full release notes,
please visit:
  https://cloud.google.com/sdk/release_notes

Once started, canceling this operation may leave your SDK installation in an inconsistent state.

Do you want to continue (Y/n)?

Performing in place update...
...

Performing post processing steps...done.

Update done!

To revert your CLI to the previously installed version, you may run:
  $ gcloud components update --version 519.0.0
```