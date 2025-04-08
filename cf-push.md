# Getting started with `cf push`

#### Note, all the instructions are intended to be copy-pasted into the terminal. 
#### The terminal can be found under applications / utilities on MacOS.  


## Prepare system 

1. **Install homebrew** (if you haven't already)  
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" `    
*[Brew](https://brew.sh/) is a package manager, and is used to install and update software*  

2. **Use Brew to install Java** (if you plan on building apps to push)  
3. `brew install openjdk@21 `  
*I had trouble with 22, so I have been using the prior release.*  

4. **Brew install Maven and Gradle**  (if you plan on building apps to push)  
`brew install maven gradle`  
*[Maven](https://maven.apache.org/) and [Gradle](https://gradle.org/) are tools used to build Java Apps*   

## Install CLI and Login  

4. **Install CF CLI**  
`brew install cloudfoundry/tap/cf-cli@8`

5. **Set CLI target**  
`cf api https://api.sys.dhaka.cf-app.com`  

6. **Login** (it will give you a link to follow to get your key)  
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

7. Sample apps you can build and push  
`https://github.com/cloudfoundry-samples`  

8. **Copy one of the sample repos**  
`git clone https://github.com/cloudfoundry-samples/hello-spring-cloud.git `

9. **Move into the downloaded app directory**  
`cd hello-spring-cloud`  
*`cd` means change directory*  

10. **Build the app**  
`mvn clean package `

## Push your App    

11. Push the built app to CF\
`cf push`
