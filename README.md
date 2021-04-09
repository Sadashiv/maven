Maven building the Java Project
===============================

Installation of archiva
=======================
which mvn
mvn -version
cd /opt/
wget https://downloads.apache.org/archiva/2.2.5/binaries/apache-archiva-2.2.5-bin.tar.gz
tar xvf apache-archiva-2.2.5-bin.tar.gz
cd apache-archiva-2.2.5
change port
vim conf/jetty.xml
./bin/archiva start
http://localhost:8091/


maven is for building the java project
maven solves the problems of manual activity and Build dependencies(third party etc)

maven is Build tool
Make dependencies/define in pom.xml maven will take care of everything.
Ant is tools need to write lengthy scripts and set of instructions to execute.

Maven describes two aspects
 I. how software is built
 II. Describe dependencies

maven downloads the software/plugins from one or more repository stored them in local cache
~/.m2

Build system

Local       <-> maven <-> remote
Repository        |        repository
                  |
                  site


Maven lifecycle

default - 23phases
clean - 2phases
site - 4phasis

Clean life cycle
pre-clean
clean
post-clean



mvn -s settings.xml clean install
mvn -s clean
mvn -s test
mvn -s install(jar get created)
Skip test cases:  -Dmaven.test.skip=true

mvn -s ~/settings.xml package -Dmaven.test.skip=true


Id: repo.external
Name: repo.external
Directory: /archiva/archiva/repositories/repo.external
Index Directory: empty
Type: Maven 2.x Repository
Cron Expression: 0 0 22 * * ?
Days Older: 30
Retention Count: 2
Description: Write
checkbox yes: Releases
checkbox yes: Snapshots
checkbox no: Block Redeployments
checkbox yes: Scanned
checkbox yes: Delete Released Snapshots
checkbox no: Staging Repository
checkbox no: Skip Packed Index creation

Id: internal
Name: Archiva Managed Internal Repository
Directory: /archiva/archiva/repositories/archiva.internal
Index Directory: /archiva/archiva/repositories/archiva.internal/.indexer
Type: Maven 2.x Repository
Cron Expression: 0 0 * * * ?
Days Older: 30
Retention Count: 2
Description: write
checkbox yes: Releases
checkbox no: Snapshots
checkbox no: Block Redeployments
checkbox yes: Scanned
checkbox yes: Delete Released Snapshots
checkbox no: Staging Repository
checkbox no: Skip Packed Index creation

