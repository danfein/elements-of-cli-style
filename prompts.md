# Prompts


## Brew (macOS package manager)

```
==> virtualbox
virtualbox requires a kernel extension to work.
If the installation fails, retry after you enable it in:
  System Preferences → Security & Privacy → General

For more information, refer to vendor documentation or this Apple Technical Note:
  https://developer.apple.com/library/content/technotes/tn2459/_index.html
```
Follow-up prompt after installing / updating a package.
Includes link to documentation about the issue.

## Oh My ZSH

```
[oh-my-zsh] Would you like to update? [Y/n] n
[oh-my-zsh] You can update manually by running `omz update`

➜  ~
```

## Google Cloud CLI

```
 google-cloud-sdk ./install.sh
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
```

## Tanzu tips

```
➜  ~ tanzu project list
Listing projects from One Tanzu Integration org

  NAME                                 AGE   INTEGRATIONS
  Example Project                      110d
  test                                 110d
  
🔎 To set your active project use 'tanzu project use NAME'

➜  ~ tanzu project use test
✓ Successfully set project to test
```