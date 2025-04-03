# Tables

## tanzu app get
```
$ tanzu app get where-for-dinner-ui

Overview
  Name:          where-for-dinner-ui
  Description:   WFD Java Microservice

Contact
  email:       foo@corp.com                  
  slack:       some-channel                  
  pagerduty:   https://url...

Source
  Image:         corp/where-for-dinner-ui@117e9..              	
  └─ Revision:   117e966faa7c57f625756eb..                  
  Git:           git@github.com:corp/where-for-dinner-ui                  
  └─ Commit:     17e966f      
     Web URL:    <url>+/tree/+<gitCommiit>           

Resources             
  cpu:          2000m                 
  memory:       500Mi (*default 128Mi)                     
  gpu.nvidia:   1
  volumes       tmp (type=tmp path=/tmp/app) (size: 1Gi)

Service bindings                 
  NAME    TYPE    BINDING
  Mysql   mysql   ServiceInstance/prod-mysql                     
  Redis   redis   missing

Availability Targets
  Name:       us-west, us-east, china-1
  Replicas:   10 replicas 

Configuration
  Cmd                      [rake]
  Args                     [web, --puma]
  Environment Variables:   IS_WORKER=false                  
                           JAVA_MAGIC_KEY=something.something                  
                           TWILIO_SOMETHING=true

🔎 For additional image information, use 'tanzu build get where-for-dinner-ui'

```