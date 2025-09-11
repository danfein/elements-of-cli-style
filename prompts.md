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
--- Decline ---
[oh-my-zsh] Would you like to update? [Y/n] n
[oh-my-zsh] You can update manually by running `omz update`

--- Approve ---
[oh-my-zsh] Would you like to update? [Y/n]
Updating Oh My Zsh
master

Features:

 - 7b51606 [brew]               Add three more aliases (#13285)
 - 2525dae [git]                Use remote default branch to guess main branch (#13212)
 - 10b750a [kompost]            Add plugin for kompose (#7729)
 - 61b144d [magic-enter plugin] Add support for jj to magic-enter plugin (#13241)
 - b9c9fcf [repo]               Auto-complete docs rebase update-refs (#13286)
 - 680298e [spackenv]           Adding Spackenv plugin (#13191)
 - 9d00a00 [tt]                 Add plugin tt (#8273)

Bug fixes:

 - 266bc17 [chruby]             Avoid adding PATH entries twice (#12980)
 - 28ac0e9 [juanghurtado]       Changed text color to red when 'root' (#7104)
 - 9ad0ce6 [magic-enter]        Avoid unexpected console output
 - 9e23925 [magic-enter]        Check for cmd existance before executing

Documentation:

 - 26863c5 [gpg-agent]          Clarify plugin purpose (#13289)

You can see the changelog with `omz changelog`
         __                                     __
  ____  / /_     ____ ___  __  __   ____  _____/ /_
 / __ \/ __ \   / __ `__ \/ / / /  /_  / / ___/ __ \
/ /_/ / / / /  / / / / / / /_/ /    / /_(__  ) / / /
\____/_/ /_/  /_/ /_/ /_/\__, /    /___/____/_/ /_/
                        /____/

Hooray! Oh My Zsh has been updated!

To keep up with the latest news and updates, follow us on X: @ohmyzsh
Want to get involved in the community? Join our Discord: Discord server
Get your Oh My Zsh swag at: Planet Argon Shop
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

## Github CLI auth
```
➜  keymaps git:(main) gh auth login
? Where do you use GitHub?  [Use arrows to move, type to filter]
> GitHub.com
  Other

 ----
? Where do you use GitHub? GitHub.com
? What is your preferred protocol for Git operations on this host?  [Use arrows to move, type to filter]
> HTTPS
  SSH

---
? Where do you use GitHub? GitHub.com
? What is your preferred protocol for Git operations on this host? HTTPS
? Authenticate Git with your GitHub credentials? (Y/n)

---
? How would you like to authenticate GitHub CLI?  [Use arrows to move, type to filter]
> Login with a web browser
  Paste an authentication token

---
? Where do you use GitHub? GitHub.com
? What is your preferred protocol for Git operations on this host? HTTPS
? Authenticate Git with your GitHub credentials? Yes
? How would you like to authenticate GitHub CLI? Login with a web browser

! First copy your one-time code: 00AA-00AA
Press Enter to open https://github.com/login/device in your browser...
✓ Authentication complete.
- gh config set -h github.com git_protocol https
✓ Configured git protocol
✓ Logged in as danfein
```