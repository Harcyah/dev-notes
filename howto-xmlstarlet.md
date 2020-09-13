# How to ... Wsl !

## From a maven pom, get project>build>plugins>maven-checkstyle-plugin>dependencies>dependency[0]>version 

`xmlstarlet sel -N pom=http://maven.apache.org/POM/4.0.0 -t -c "//pom:project/pom:build/pom:plugins/pom:plugin[.//pom:artifactId = 'maven-checkstyle-plugin']/pom:dependencies/pom:dependency[1]/pom:version" pom.xml`
