# Updates

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