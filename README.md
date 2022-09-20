# Description
Purpose is to have command to download maven dependency. With support for version ranges.

# examples  
can be executed in windows "cmd" (mvn has to be installed)

#### Just all default
`mvn dependency:copy-dependencies -DoutputDirectory=./downloaded-dependencies`
                                           
#### Support for version ranges e.g **[1.0,2.0)**
`mvn dependency:copy-dependencies -DoutputDirectory=./downloaded-dependencies -Ddep.group="org.apache.logging.log4j" -Ddep.artifact="log4j-api" -Ddep.version="[2.17.1,)"`

#### With artifact type
`mvn dependency:copy-dependencies -DoutputDirectory=./downloaded-dependencies -Ddep.group="org.apache.logging.log4j" -Ddep.artifact="log4j-api" -Ddep.version="[2.17.1,)" -Ddep.type=pom`

# Alternative solutions

### maven-dependency-plugin:get
This is just commands, which works: 
  + ADVANTAGE do not need help pom.xml.
  - DISADVANTAGE has NO support for version ranges

e.g. for windows "cmd":  
`mvn org.apache.maven.plugins:maven-dependency-plugin:2.1:get -Dartifact="org.apache.commons:commons-lang3:3.12.0" -DrepoUrl="http://repo1.maven.apache.org/maven2" -Ddest=downloaded.jar`