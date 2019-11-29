# How to ... Intellij !

##  : Create unit or integration tests configuration

- Create JUnit run/debug configuration
- Use `Pattern` test kind
- Set pattern to `^.*IntegrationTest$` to only run integration tests
- Set pattern to `^(?!.*IntegrationTest$).*$` to only run unit tests

This configuration obviously depends on a correct class naming pattern :)
