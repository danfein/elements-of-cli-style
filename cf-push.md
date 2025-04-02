## Getting started with `cf push`

******* Prepare system *******

Install homebrew (if you haven't already)
`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)" `

Use Brew to install Java (if you haven't already)
`brew install openjdk@21 ` //I had trouble with 22, so I have been using the prior release.

Use brew to install Maven and Gradle (which we can use to build our Java Apps)
`brew install maven gradle` //you can install both from the same command


******* Install CLI and Login *******  

Install CF CLI 
`brew install cloudfoundry/tap/cf-cli@8`

Set CLI target
`cf api https://api.sys.dhaka.cf-app.com`

Login (it will give you a link to follow to get your key)
`cf login --sso `

******* Get an App *******  

Sample apps you can build and push
`https://github.com/cloudfoundry-samples`

Copy one of the sample repos
`git clone https://github.com/cloudfoundry-samples/hello-spring-cloud.git `

Move into the downloaded directory
`cd hello-spring-cloud`

Build the app
`mvn clean package`

******* Push your App *******  

Push the built app to CF
'cf push'
