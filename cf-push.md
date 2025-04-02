## Getting started with `cf push`

#### Note, all the instructions are intended to be copy-pasted into the terminal. 
#### The terminal can be found under applications / utilities on MacOS.  


******* Prepare system *******  

**Install homebrew** (if you haven't already)  
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" `    
*[Brew](https://brew.sh/) is a package manager, and is used to install and update software*  

**Use Brew to install Java** (if you haven't already)  
`brew install openjdk@21 `  
*I had trouble with 22, so I have been using the prior release.*  

**Brew install Maven and Gradle** 
`brew install maven gradle`  
*[Maven](https://maven.apache.org/) and [Gradle](https://gradle.org/) are tools used to build Java Apps*   

******* Install CLI and Login *******  

**Install CF CLI**  
`brew install cloudfoundry/tap/cf-cli@8`

**Set CLI target**  
`cf api https://api.sys.dhaka.cf-app.com`  

**Login** (it will give you a link to follow to get your key)  
`cf login --sso `  

******* Get an App *******  

Sample apps you can build and push  
`https://github.com/cloudfoundry-samples`  

**Copy one of the sample repos**  
`git clone https://github.com/cloudfoundry-samples/hello-spring-cloud.git `

**Move into the downloaded app directory**  
`cd hello-spring-cloud`  
*`cd` means change directory*  

**Build the app**  
`mvn clean package `

******* Push your App *******  

Push the built app to CF\
`cf push`
