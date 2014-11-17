# Play framework 2.35 with scala 2.11.2 scoverage rpm maven-site
Dependencies are handled by maven

# Introduction
Why this project - maven integration in an IDE is far better than sbt integration

## Features
  - Multi modules dependencies don't need to be installed inside eclipse + update dependencies without re-importing or running play eclipse ... 
  - This project aim to industrialize play2 akka with maven
  - Single versions modules (modules use the parent version) - use mvn version plugin for versionning 
  
## Import in eclipse
  - Import existing maven project
  - Install Scala IDE from [update site Kepler](<http://download.scala-ide.org/sdk/helium/e38/scala211/stable/site/>) or [dev update site Kepler](<http://download.scala-ide.org/sdk/lithium/e38/scala211/dev/site/>) or [dev update site Juno](<http://download.scala-ide.org/sdk/lithium/e44/scala211/dev/site/>)

        - Add update site
		- Choose Scala IDE and Scala IDE Plugins
		- Continue and finish install
   - Add scala project nature on project module
   
	           Right click on module project go to the end Configure --> Add Scala Nature

## Install first
		mvn clean install

## launch
		./activator start/stop
or

		mvn play2:start/stop

#### Hot reload with debugging
		./activator debug ~run


### Build rpm package (tested on centos for centos needs rpmbuild)
		./activator rpm:packageBin
or

		mvn package -P with-rpm

### Produce rpm and deploy it with your jars (code and source code) to your repository
		mvn deploy -P with-rpm
  - uses a different repository for snapshots and releases

### Produce reporting maven-site with scala doc and scoverage (code coverage)
		mvn site site:deploy


### No duplicate jars between maven local repo and ivy local repo
  - sbt will check ivy local repository then maven local repository for dependencies then standard sbt scala repositories
  
  

# Big Thanks to [gslowikowski](<https://github.com/gslowikowski>) who developed most of the plugins used here.
    
                               