# Help Text

##Pihole (dns adblocker)

```
Usage: pihole [options]
Example: 'pihole -w -h'
Add '-h' after specific commands for more information on usage

Whitelist/Blacklist Options:
  -w, whitelist       Whitelist domain(s)
  -b, blacklist       Blacklist domain(s)
  --regex, regex      Regex blacklist domains(s)
  --white-regex       Regex whitelist domains(s)
  --wild, wildcard    Wildcard blacklist domain(s)
  --white-wild        Wildcard whitelist domain(s)
                        Add '-h' for more info on whitelist/blacklist usage

Debugging Options:
  -d, debug           Start a debugging session
                        Add '-a' to automatically upload the log to tricorder.pi-hole.net
  -f, flush           Flush the Pi-hole log
  -r, reconfigure     Reconfigure or Repair Pi-hole subsystems
  -t, tail [arg]      View the live output of the Pi-hole log.
                      Add an optional argument to filter the log
                      (regular expressions are supported)


Options:
  -a, admin           Web interface options
                        Add '-h' for more info on Web Interface usage
  -c, chronometer     Calculates stats and displays to an LCD
                        Add '-h' for more info on chronometer usage
  -g, updateGravity   Update the list of ad-serving domains
  -h, --help, help    Show this help dialog
  -l, logging         Specify whether the Pi-hole log should be used
                        Add '-h' for more info on logging usage
  -q, query           Query the adlists for a specified domain
                        Add '-h' for more info on query usage
  -up, updatePihole   Update Pi-hole subsystems
                        Add '--check-only' to exit script before update is performed.
  -v, version         Show installed versions of Pi-hole, Web Interface & FTL
                        Add '-h' for more info on version usage
  uninstall           Uninstall Pi-hole from your system
  status              Display the running status of Pi-hole subsystems
  enable              Enable Pi-hole subsystems
  disable             Disable Pi-hole subsystems
                        Add '-h' for more info on disable usage
  restartdns          Full restart Pi-hole subsystems
                        Add 'reload' to update the lists and flush the cache without restarting the DNS server
                        Add 'reload-lists' to only update the lists WITHOUT flushing the cache or restarting the DNS server
  checkout            Switch Pi-hole subsystems to a different GitHub branch
                        Add '-h' for more info on checkout usage
  arpflush            Flush information stored in Pi-hole's network tables
```

Grouped by functions
Flags use a mix of single and double dashes