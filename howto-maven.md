# How to ... Maven !

## Run a plugin execution from CLI [source](https://stackoverflow.com/questions/3166538/how-to-execute-maven-plugin-execution-directly-from-command-line/28642594)

```
mvn <plugin group>:<plugin artifact>:<plugin goal>@<execution id>
```

## Skip tests
```
mvn clean package -Dmaven.test.skip
```
