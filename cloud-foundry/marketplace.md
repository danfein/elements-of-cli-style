# cf Marketplace

## Help
```
$ cf marketplace -h
NAME:
   marketplace - List available offerings in the marketplace

USAGE:
   cf marketplace [-e SERVICE_OFFERING] [-b SERVICE_BROKER] [--no-plans]

ALIAS:
   m

OPTIONS:
   -e                      Show plan details for a particular service offering
   -b                      Only show details for a particular service broker
   --no-plans              Hide plan information for service offerings
   --show-unavailable      Show plans that are not available for use

SEE ALSO:
   create-service, services
```

## List
```
cf marketplace
Getting all service offerings from marketplace in org student-mtntl7 / space default as student-mtntl7...

offering   plans                                               description                                                                                                                      broker
postgres   on-demand-postgres-db                               Postgres service to provide on-demand dedicated instances configured as database.                                                postgres-odb
genai      chat-and-tools-model, chat-model, embedding-model   GenAI on Tanzu Platform for Cloud Foundry provides integrations with a wide range of generative AI models via an AI API proxy.   genai-service

TIP: Use 'cf marketplace -e SERVICE_OFFERING' to view descriptions of individual plans of a given service offering.
```

## Get
```
$ cf marketplace -e genai
Getting service plan information for service offering genai in org student-mtntl7 / space default as student-mtntl7...

broker: genai-service
   plan                   description                               free or paid   costs
   chat-and-tools-model   A model with chat and tool capabilities   free           
   chat-model             A model with chat capabilities            free           
   embedding-model        A high-performing open embedding model    free           
```

## Create
```
$ cf create-service genai chat-and-tools-model chat-llm
Creating service instance chat-llm in org student-mtntl7 / space default as student-mtntl7...

Service instance chat-llm created.
OK
```

## Bind
```
$ cf bind-service ai-tool-chat chat-llm
Binding service instance chat-llm to app ai-tool-chat in org student-mtntl7 / space default as student-mtntl7...
OK

TIP: Use 'cf restage ai-tool-chat' to ensure your env variable changes take effect
```

## Create User Provided Service
```
$ cf cups mcp-time-server -p '{"mcpServiceURL":"https://time-mcp-server-quick-mouse-py.apps.vent-7124.cf-app.com"}
'
Creating user provided service mcp-time-server in org student-mtntl7 / space default as student-mtntl7...
OK
```

```
cf delete-service mcp-time-server
This action impacts all resources scoped to this service instance, including service bindings, service keys and route bindings.
This will remove the service instance from any spaces where it has been shared.
Really delete the service instance mcp-time-server? [yN]: y
Deleting service instance mcp-time-server in org student-mtntl7 / space default as student-mtntl7...

Service instance mcp-time-server deleted.
OK
```