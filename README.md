# Englishtown oss-parent
This should be the parent pom for Englishtown open source projects.


# Configuration
Add the following to your pom:

```xml
    <parent>
        <groupId>com.englishtown</groupId>
        <artifactId>oss-parent</artifactId>
        <version>1.2.0</version>
    </parent>
```

Also add distribution site and scm elements.  These cannot be added in the parent do this issue
http://jira.codehaus.org/browse/SCM-531

```xml
    <distributionManagement>
        <site>
            <id>sling.englishtown.com</id>
            <url>
                dav:https://sling.englishtown.com/content/docs/${project.groupId}/${project.artifactId}/${project.version}
            </url>
        </site>
    </distributionManagement>

    <!--Copy the below and uncomment in your pom-->
    <scm>
        <connection>scm:git:https://github.com/englishtown/${project.artifactId}.git</connection>
        <developerConnection>scm:git:ssh://git@github.com/englishtown/${project.artifactId}.git</developerConnection>
        <tag>HEAD</tag>
        <url>https://github.com/englishtown/${project.artifactId}</url>
    </scm>
```


# Example commands

## Snapshot deployment
mvn clean package deploy

## Release deployment
mvn clean package gpg:sign deploy
