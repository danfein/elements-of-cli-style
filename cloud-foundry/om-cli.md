# om cli for opsmanager

Install
```
$ brew tap pivotal-cf/om https://github.com/pivotal-cf/om
$ brew install om
```

Help
```
 $ om -h

Usage:
  om [OPTIONS] <command>

Application Options:
      --ca-cert=               OpsManager CA certificate path or value [$OM_CA_CERT]
  -c, --client-id=             Client ID for the Ops Manager VM (not required for unauthenticated commands) [$OM_CLIENT_ID]
  -s, --client-secret=         Client Secret for the Ops Manager VM (not required for unauthenticated commands)
                               [$OM_CLIENT_SECRET]
  -o, --connect-timeout=       timeout in seconds to make TCP connections (default: 10) [$OM_CONNECT_TIMEOUT]
  -d, --decryption-passphrase= Passphrase to decrypt the installation if the Ops Manager VM has been rebooted (optional for most
                               commands) [$OM_DECRYPTION_PASSPHRASE]
  -e, --env=                   env file with login credentials
  -p, --password=              admin password for the Ops Manager VM (not required for unauthenticated commands) [$OM_PASSWORD]
  -r, --request-timeout=       timeout in seconds for HTTP requests to Ops Manager (default: 1800) [$OM_REQUEST_TIMEOUT]
  -k, --skip-ssl-validation    skip ssl certificate validation during http requests [$OM_SKIP_SSL_VALIDATION]
  -t, --target=                location of the Ops Manager VM [$OM_TARGET]
      --uaa-target=            optional location of the Ops Manager UAA [$OM_UAA_TARGET]
      --trace                  prints HTTP requests and response payloads [$OM_TRACE]
  -u, --username=              admin username for the Ops Manager VM (not required for unauthenticated commands) [$OM_USERNAME]
      --vars-env=              load vars from environment variables by specifying a prefix (e.g.: 'MY' to load MY_var=value)
                               [$OM_VARS_ENV]
  -v, --version                prints the om release version

Help Options:
  -h, --help                   Show this help message

Available commands:
  activate-certificate-authority  activates a certificate authority on the Ops Manager
  apply-changes                   triggers an install on the Ops Manager targeted
  assign-multi-stemcell           assigns multiple uploaded stemcells to a product in the targeted Ops Manager 2.6+
  assign-stemcell                 assigns an uploaded stemcell to a product in the targeted Ops Manager
  available-products              **DEPRECATED** lists available products. Use 'products --available' instead.
  bosh-diff                       displays BOSH manifest diff for the director and products
  bosh-env                        prints environment variables for BOSH and Credhub
  certificate-authorities         lists certificates managed by Ops Manager
  certificate-authority           prints requested certificate authority
  config-template                 generates a config template from a Pivnet product
  configure-authentication        configures Ops Manager with an internal userstore and admin user account
  configure-director              configures the director
  configure-ldap-authentication   configures Ops Manager with LDAP authentication
  configure-opsman                configures values present on the Ops Manager settings page
  configure-product               configures a staged product
  configure-saml-authentication   configures Ops Manager with SAML authentication
  create-certificate-authority    creates a certificate authority on the Ops Manager
  create-vm-extension             creates/updates a VM extension
  credential-references           list credential references for a deployed product
  credentials                     fetch credentials for a deployed product
  curl                            issues an authenticated API request
  delete-certificate-authority    deletes a certificate authority on the Ops Manager
  delete-installation             deletes all the products on the Ops Manager targeted
  delete-product                  deletes an unused product from the Ops Manager
  delete-ssl-certificate          deletes certificate applied to Ops Manager
  delete-unused-products          deletes unused products on the Ops Manager targeted
  deployed-manifest               prints the deployed manifest for a product
  deployed-products               **DEPRECATED** lists deployed products. Use 'products --deployed' instead.
  diagnostic-report               reports current state of your Ops Manager
  disable-director-verifiers      disables director verifiers
  disable-product-verifiers       disables product verifiers
  download-product                downloads a specified product file from Pivotal Network
  errands                         list errands for a product
  expiring-certificates           lists expiring certificates from the Ops Manager targeted
  expiring-licenses               lists expiring licenses from the Ops Manager targeted
  export-installation             exports the installation of the target Ops Manager
  generate-certificate            generates a new certificate signed by Ops Manager's root CA
  generate-certificate-authority  generates a certificate authority on the Opsman
  import-installation             imports a given installation to the Ops Manager targeted
  installation-log                output installation logs
  installations                   list recent installation events
  interpolate                     interpolates variables into a manifest
  pending-changes                 checks for pending changes
  pre-deploy-check                checks completeness and validity of product configuration
  product-metadata                prints product metadata
  products                        lists product staged, available, and deployed versions
  regenerate-certificates         deletes all non-configurable certificates in Ops Manager so they will automatically be regenerated on the next apply-changes
  revert-staged-changes           This command reverts the staged changes already on an Ops Manager.
  ssl-certificate                 gets certificate applied to Ops Manager
  stage-product                   stages a given product in the Ops Manager targeted
  staged-config                   generates a config from a staged product
  staged-director-config          generates a config from a staged director
  staged-manifest                 prints the staged manifest for a product
  staged-products                 **DEPRECATED** lists staged products. Use 'products --staged' instead.
  unstage-product                 unstages a given product from the Ops Manager targeted
  upload-product                  uploads a given product to the Ops Manager targeted
  upload-stemcell                 uploads a given stemcell to the Ops Manager targeted
  version                         prints the om release version
  vm-lifecycle                    commands to manage the state of the Ops Manager VM (aliases: nom)
```

## Login
```
$ uaac target https://ops-manager.url.cf-app.com/uaa
Unknown key: Max-Age = 86400
Unknown key: SameSite = Lax

Target: https://ops-manager.url.cf-app.com/uaa

$  om-workspace uaac token sso get
Client ID:  opsman
Client secret:
Unknown key: Max-Age = 86400
Unknown key: SameSite = Lax
Passcode ( from https://ops-manager.dhaka.cf-app.com/uaa/passcode ):  ************
WARNING: Decoding token without verifying it was signed by its authoring UAA

Successfully fetched token via owner passcode grant.
Target: https://ops-manager.dhaka.cf-app.com/uaa
Context: df009256, from client opsman
```

## Errors
```
--- No Auth ---
$ om products
2025/09/24 08:50:00 failed to retrieve staged and deployed products could not make api request to diagnostic_report endpoint: could not send api request to GET /api/v0/diagnostic_report: could not parse Opsman target URL: target flag is required, run `om help` for more info
```