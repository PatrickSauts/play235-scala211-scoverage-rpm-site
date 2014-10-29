# Play framework 2.35 with scala 2.11.2 scoverage rpm maven-site
Dependencies are handled by maven

# Introduction
Why this project - maven integration in an IDE is far better than sbt integration

## Features
  - Multi modules dependencies don't need to be installed + update dependencies without re-importing or running play eclipse ... 
  - This project aim to industrialize play2 akka with maven
  - Single versions modules (modules use the parent version) - use mvn version plugin for versionning 
  
## launch
		./activator start/stop
or

		mvn play2:start/stop

#### hot relaod with debugging
		./activator debug ~run


### Build rpm package (tested on centos for centos needs rpmbuild)
		./activator rpm:packageBin<br>
or

		mvn package -p with-rpm<br>

### Produce rpm and deploy it with your jars (code and source code) to your repository<br>
		mvn deploy -P with-rpm<br>
  - use a different repository for snapshots and released<br>

### Produce reporting maven-site with scala doc and scoverage (code coverage)
		mvn site site:deploy


### No duplicate jars between maven local repo and ivy local repo
  - sbt will check ivy local repository then maven local repository for dependencies then standard sbt scala repositories
  
  

# A Big Thanks you to [gslowikowski](<https://github.com/gslowikowski>) who developed most of the plugins used here.
    
                               