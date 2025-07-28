# CLI accessibility 

## GCP CLI
- [GCP documentation](https://cloud.google.com/sdk/docs/enabling-accessibility-features)
```
$ gcloud config set accessibility/screen_reader true
```
- Flattens tables, removing ascii borders
- Replace progress feedback spinners to plaintext "working", output to stderr
- Replace progess bars with a plaintext percentage value, output to stderr
- Note: outputting to stderr could allow automation to watch stdout only, and ignore the status updates that may primarally be useful for human users.