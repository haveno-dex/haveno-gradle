# How to upgrade the Gradle version

Visit the [Gradle website](https://gradle.org/releases) and decide the:

 - desired version
 - desired distribution type
 - what is the sha256 for the version and type chosen above

Adjust the following command with tha arguments above and execute it twice:

```asciidoc
$ ./gradlew wrapper --gradle-version 8.5 \
    --distribution-type bin \
    --gradle-distribution-sha256-sum 9d926787066a081739e8200858338b4a69e837c3a821a33aca9db09dd4a41026
```

The first execution should automatically update:

- `haveno-gradle/gradle/wrapper/gradle-wrapper.properties`

The second execution should then update:

- `haveno-gradle/gradle/wrapper/gradle-wrapper.jar`
- `haveno-gradle/gradlew`
- `haveno-gradle/gradlew.bat`

The four updated files are ready to be committed.
