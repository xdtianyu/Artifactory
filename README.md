# Artifactory

Deploy aar and pom files to artifactory.

## Howto

1\. In project root `build.gradle` file, define pom configures:

```groovy
buildscript {
    ext {
        pom_group = 'org.example'
        pom_version = '1.0.0'
        pom_project_url = "https://github.com/example/example"
        pom_developer_id = "example"
        pom_developer_name = "example"
        pom_developer_email = "example@gmail.com"
        # pom_description = ""
        # pom_license = ""
        # pom_license_url = ""
        # pom_license_distribution = ""
    }

    dependencies {
        ...
        classpath "org.jfrog.buildinfo:build-info-extractor-gradle:4.10.0"
    }
}
```

2\. In project root `gradle.properties` file, define artifactory configures:

```
artifactory_contextUrl=https://maven.example.com/artifactory/
artifactory_user=username
artifactory_password=password
```

3\. Add the follow line to your module's `build.gradle` file

```
apply from: "https://raw.githubusercontent.com/xdtianyu/Artifactory/master/maven-publish.gradle"
```

4\. Deploy

```
./gradlew clean artifactoryPublish
```
