# cf push

## Application components
App: The top-level resource that represents an app and its configuration.

Package: The source code that makes up an app.

Build: The staging process. Creating a build combines a package with a buildpack, and builds it into an executable resource.

Droplet: An executable resource created in a build.

Manifest: A file used to apply configuration to an app and its underlying processes.

## Getting started Walkthrough
#### Note, all the instructions are intended to be copy-pasted into the terminal. 
#### The terminal can be found under applications / utilities on MacOS.  


## Prepare system 

1. **Install homebrew**  
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" `    
*[Brew](https://brew.sh/) is a package manager, and is used to install and update software*  

2. **Use Brew to install Java** (if you plan on building apps to push)  
`brew install openjdk@21 `  
*I had trouble with 22, so I have been using the prior release.*  

3. **Brew install Maven and Gradle**  (if you plan on building apps to push)  
`brew install maven gradle`  
*[Maven](https://maven.apache.org/) and [Gradle](https://gradle.org/) are tools used to build Java Apps*   

## Install CLI and Login  

1. **Install CF CLI**  
`brew install cloudfoundry/tap/cf-cli@8`

2. **Set CLI target**  
`cf api https://api.sys.dhaka.cf-app.com`  

3. **Login** (it will give you a link to follow to get your key)  
`cf login --sso `  

## Prepare Environment  
#### GUI
1. **Login to [AppsMan](https://apps.sys.dhaka.cf-app.com/)**  
2. Create Org and Space  

#### CLI
1. **Create Org**  
`cf create-org example-name`
2. **Target Org**  
`cf target -o example-name`  
4. **Create Space**  
`cf create-space example-name`
2. **Target Space**  
`cf target -s example-name`  

## Get an App  

1. Sample apps you can build and push  
`https://github.com/cloudfoundry-samples`  

2. **Copy one of the sample repos**  
`git clone https://github.com/cloudfoundry-samples/hello-spring-cloud.git `

3. **Move into the downloaded app directory**  
`cd hello-spring-cloud`  
*`cd` means change directory*  

4. **Build the app**  
`mvn clean package `

## Push your App    

1. Push the built app to CF\
`cf push`
---  


## Sub step deployment
Used to isolate deployment steps, can be used to 
- retry failed stages
- scan a droplet before deployment
- integrate with change request system
```
--- Create ---
$ cf create-app training-app
Creating app training-app in org student-pqvsjp / space default as student-pqvsjp...
OK


--- Package ---
$ cf create-package training-app -p training-app.zip
Creating and uploading bits package for app training-app in org student-pqvsjp / space default as student-pqvsjp...
Package with guid '4c5fa6df-2332-492c-a08a-2b32bd8879f0' has been created.
OK

--- verify package ---
$ cf packages training-app
Getting packages of app training-app in org student-pqvsjp / space default as student-pqvsjp...

guid                                   state   created
4c5fa6df-2332-492c-a08a-2b32bd8879f0   ready   Tue 06 May 22:08:26 UTC 2025

--- Apply Manifest ---
$ cf apply-manifest -f manifest.yml
Applying manifest manifest.yml in org student-pqvsjp / space default as student-pqvsjp...

Updating with these attributes...
  ---
  applications:
  - name: training-app
    disk-quota: 256M
-   instances: 1
+   instances: 3
    path: ./training-app.zip
    memory: 48M
+   buildpacks:
+   - go_buildpack
+   env:
+     TRAINING_KEY_2: training-value-2
+     TRAINING_KEY_3: training-value-3_1
+   metadata:
+     labels:
+       env: dev
+       sensitive: true
+   services:
+   - training-app-db

OK

--- Stage ---
$ cf stage training-app --package-guid 4c5fa6df-2332-492c-a08a-2b32bd8879f0
Staging package for training-app in org student-pqvsjp / space default as student-pqvsjp...
   Downloading go_buildpack...
   Downloaded go_buildpack
   Cell bb5049a2-a25d-49bf-accd-51eba9084290 creating container for instance a3b23da4-5f47-4048-90a1-6eaa7398b75a
   Security group rules were updated
   ...
      Exit status 0
   Uploading droplet, build artifacts cache...
   Uploading droplet...
   Uploading build artifacts cache...
   Uploaded build artifacts cache (16.7M)
   Uploaded droplet (5.7M)
   Uploading complete
   Cell bb5049a2-a25d-49bf-accd-51eba9084290 stopping instance a3b23da4-5f47-4048-90a1-6eaa7398b75a
   Cell bb5049a2-a25d-49bf-accd-51eba9084290 destroying container for instance a3b23da4-5f47-4048-90a1-6eaa7398b75a

Package staged
droplet guid:   104916f5-ff97-425b-83a1-00f7f22c1ef2
state:          staged
created:        Tue 06 May 22:13:13 UTC 2025

--- verify ---
$ cf droplets training-app
Getting droplets of app training-app in org student-pqvsjp / space default as student-pqvsjp...

guid                                   state    created
104916f5-ff97-425b-83a1-00f7f22c1ef2   staged   Tue 06 May 22:14:02 UTC 2025

--- Set Droplet ---
$ cf set-droplet training-app 104916f5-ff97-425b-83a1-00f7f22c1ef2
Setting app training-app to droplet 104916f5-ff97-425b-83a1-00f7f22c1ef2 in org student-pqvsjp / space default as student-pqvsjp...
OK

--- Start App ---
$ cf start training-app
Starting app training-app in org student-pqvsjp / space default as student-pqvsjp...

Waiting for app to start...

Instances starting...
Instances starting...
Instances starting...

name:              training-app
requested state:   started
routes:            
last uploaded:     Tue 06 May 22:14:02 UTC 2025
stack:             cflinuxfs4
buildpacks:        
        name           version   detect output   buildpack name
        go_buildpack   1.10.26   go              go

type:           web
sidecars:       
instances:      3/3
memory usage:   48M
     state     since                  cpu    memory     disk       logging        cpu entitlement   details
#0   running   2025-05-06T22:18:26Z   0.0%   0B of 0B   0B of 0B   0B/s of 0B/s   0.0%              
#1   running   2025-05-06T22:18:25Z   0.0%   0B of 0B   0B of 0B   0B/s of 0B/s   0.0%              
#2   running   2025-05-06T22:18:26Z   0.0%   0B of 0B   0B of 0B   0B/s of 0B/s   0.0%    
```
