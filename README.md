Please read the documentation available here:
http://trac.mapfish.org/trac/mapfish/wiki/PrintModuleDoc

NOTE: This fork was created because official 1.2-SNAPSHOT has severe regressions after spring dependency
was introduced. The fork was done based on commit fe62ee6423f843b3b8e8ecef9bf40cd31a531e43, just before
spring dependency was introduced. 

Since the fork the artifact has been renamed to 1.2-SWECO.

To install to local maven repo:
 > ./gradlew install

---

== build ==
- Execute the following command():
  > ./gradlew build

This will build three artifacts:  print-servlet-xxx.war, print-lib.jar, print-standalone.jar

== Deploy ==
The following command will build and upload all artifacts to the dev.mapfish.org repository.
  > ./gradlew upload -DsshPassphrase=... 

To use in eclipse:
- Create eclipse project metadata:
  > ./gradlew eclipse
- Import project into eclipse

== Run from commandline ==
The following command will run the mapfish printer.  If you do no supply any -Dxxx args then all argument options will be listed.
  > ./gradlew run -Dconfig=samples/config.yaml -Dspec=samples/spec.json -Doutput=/tmp/print-out.pdf
  
== Run in eclipse ==
- Create new Java Run Configuration
- Main class is org.mapfish.print.ShellMapPrinter
- Program arguments: --config=samples/config.yaml --spec=samples/spec.json --output=$HOME/print.pdf
