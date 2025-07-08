# cf cli plugins

## cf plugins
```
--- list ---
$ cf plugins
Listing installed plugins...

plugin         version   command name   command help
usage-report   1.4.0     usage-report   Report AI and memory usage for orgs and spaces

Use 'cf repo-plugins' to list plugins in registered repos available to install.

--- installation --- 
$ cf install-plugin "Usage Report"
Searching CF-Community for plugin Usage Report...
Plugin Usage Report 1.4.0 found in: CF-Community
Attention: Plugins are binaries written by potentially untrusted authors.
Install and use plugins at your own risk.
Do you want to install the plugin Usage Report? [yN]: y
Starting download of plugin binary from repository CF-Community...
 7.58 MiB / 7.58 MiB [====================================================================================================================================] 100.00% 0s
Installing plugin usage-report...
OK

Plugin usage-report 1.4.0 successfully installed.

--- use ---
$ cf usage-report
Org student-pqvsjp is consuming 144 MB of 256 MB.
        Space default is consuming 144 MB memory (56%) of org quota.
                2 apps: 1 running 1 stopped
                4 instances: 3 running, 1 stopped
You are running 2 apps in 1 org(s), with a total of 4 instances.
```