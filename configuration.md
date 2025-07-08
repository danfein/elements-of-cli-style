# Configuration

## cf localization
```
--- form ---
cf config --locale <LOCALE>

--- example ---
cf config --locale fr-FR

--- unset ---
cf config --locale CLEAR 
```
 - note: clear defaults to english

 ## cf tracing
 ```
--- Envar ---
CF_TRACE=TRUE

--- Flag ---
cf config --trace=true
 ```
 - cf config --trace=true