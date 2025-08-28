# Delete

## cf CLI delete confirmation
```
--- space ---

$ cf delete-space temp
This action impacts all resources scoped to this space, including apps, service instances, and space-scoped service brokers.
Really delete the space temp? [yN]: y
Deleting space temp in org dftest as daniel.fein@company.com...
OK

Really delete the space temp? [yN]: n
'temp' has not been deleted.

--- org ---
$ cf delete-org dftest
Really delete the org dftest, including its spaces, apps, service instances, routes, private domai
ns and space-scoped service brokers? [yN]:n
Organization 'dftest' has not been deleted.

--- app --- 
$ cf delete hello-spring-cloud
Really delete the app hello-spring-cloud? [yN]: n
App 'hello-spring-cloud' has not been deleted.

--- route ---
cf delete-route apps.dhaka.cf-app.com
This action impacts all apps using this route.
Deleting this route will make apps unreachable via this route.
Really delete the route apps.dhaka.cf-app.com? [yN]:n
'apps.dhaka.cf-app.com' has not been deleted.

--- service ---
$ cf delete-service hello-scaler
This action impacts all resources scoped to this service instance, including service bindings, service keys and route bindings.
This will remove the service instance from any spaces where it has been shared.
Really delete the service instance hello-scaler? [yN]:
Delete cancelled

--- service binding ---
cf unbind-service hello-spring-cloud hello-scaler
Unbinding app hello-spring-cloud from service hello-scaler in org dftest / space temp as daniel.fein@broadcom.com...
OK
```