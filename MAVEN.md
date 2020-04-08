# MAVEN

## Show all updatable project dependencies
```
    mvn versions:display-dependency-updates
```

## Show all updatable project plugins
```
    mvn versions:display-plugin-updates
```

## Filter output of Maven Dependency Analysis
```
    mvn dependency:analyze | egrep -i "warning[^.]+[a-zA-Z]+|info.*building" > analyze.txt
```

# Increase project version including of maven project modules
```
    mvn versions:set -DnewVersion=1.0.0
    mvn versions:commit
```

## Tomcat Debug OPT for Maven
```
    export MAVEN_OPTS="$MAVEN_OPTS -Xdebug -Xnoagent -Djava.compiler=NONE -Xrunjdwp:transport=dt_socket,address=5005,server=y,suspend=n"
```
