# logging in to cf
For humans
```
cf login
cf login --sso
```
- Credenials are provided interactivly, or (less ideally) via flags
- The CLI will attempt to set the org and space targets

For automation
```
cf auth
```
- Creds are provided via envars
- The CLI will not set your target