SonarQube Setup
==============

Contents
----
*   [A. Program Analysis Method](#a-)
*   [B. Information Sources](#b-)


A. Program Analysis Method
----------------------------
The Jenkins nodes (**java**, **nodejs**, etc.) included as standard in Pocci
incorporate the information necessary for program analysis in SonarQube as environmental variables.
They can be used to configure the settings for connecting with SonarQube.

Environment variable example:
*   **SONAR_URL:** URL of SonarQube
*   **SONAR_DB_HOST:** Host name of SonarQube database
*   **SONAR_DB_PORT:** Port number of SonarQube database

For details on other environment variables that can be used,
refer to [sonar: section of Setup File Reference]  (./setup-yml.en.md#sonar-).


### Java program setting example
A Java program can be analyzed by configuring the settings
for `pom.xml` as shown below and then using
**SonarQube Maven Plugin** (executing `mvn sonar:sonar`).

```xml
<properties>
    <sonar.jdbc.url>jdbc:postgresql://${env.SONAR_DB_HOST}:${env.SONAR_DB_PORT}/${env.SONAR_DB_NAME}</sonar.jdbc.url>
    <sonar.jdbc.username>${env.SONAR_DB_USER}</sonar.jdbc.username>
    <sonar.jdbc.password>${env.SONAR_DB_PASS}</sonar.jdbc.password>
    <sonar.host.url>${env.SONAR_URL}</sonar.host.url>
</properties>
```

* For the overall settings, refer to
    `pom.xml` and `build.sh` of
    `template/code/example/example-java`.


### JavaScript program setting example
A JavaScript program can be analyzed by configuring
the settings for `Gruntfile.js` as shown below using **grunt-sonar-runner**.

```javascript
sonarRunner:  {
  analysis:  {
    options:  {
      sonar:  {
        host:  {
          url:  process.env.SONAR_URL
        },
        jdbc:  {
          url:  'jdbc:postgresql://' + process.env.SONAR_DB_HOST + ':' + process.env.SONAR_DB_PORT + '/' + process.env.SONAR_DB_NAME,
          username:  process.env.SONAR_DB_USER,
          password:  process.env.SONAR_DB_PASS
        },
        ...
      }
    }
  }
}
```

* For the overall settings, refer to
    refer to `Gruntfile.js` and `karma.conf.js` of
    `template/code/example/example-nodejs`.


B. Information Sources
------------------------
*   [SonarQube] (http://www.sonarqube.org/)
*   [SonarQube - Analyzing with Maven] (http://docs.sonarqube.org/display/SONAR/Analyzing+with+Maven)
*   [SonarQube Mave Plugin] (http://www.mojohaus.org/sonar-maven-plugin/)
*   [grunt-sonar-runner] (https://www.npmjs.com/package/grunt-sonar-runner)
