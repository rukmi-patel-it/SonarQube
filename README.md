# SonarQube

Run below command to download docker containers to run sonar-qube web server.

```
docker-compose up -d --build
```

# Sonar Scanner
 To install sonar-scanner, Please go to - https://docs.sonarsource.com/sonarqube-server/10.4/analyzing-source-code/scanners/sonarscanner/

 You can download and install sonar-scanner as per your operating system. 

 Mac uses can simply run `brew install sonar-scanner`.


# Steps to run sonar-qube web server.

1. Run http://localhost:9001/ in browser. If 9001 port is busy for you and you have run `sonarqube` container on any other port then use that port.

2. If you are trying to login for the first time, use below credentials.
    - *Username:* admin
    - *Password:* admin

3. The system will ask to change credentials immediately after you logged in for the first time. I recommend to change it. You would be redirected to http://localhost:9001/account/reset_password

4. On http://localhost:9001/projects, you will be shown `Add a project` button. Click on it.

5. You would be shown multiple options. Choose as your convenience. Complete those steps to generate token.

6. Now go to root folder of the project for which you need to generate sonar report.

7. Run below command where you need to replace [PROJECT_KEY] and [TOKEN] with your own values.

    ```
    sonar-scanner \
        -Dsonar.projectKey=[PROJECT_KEY] \
        -Dsonar.sources=. \
        -Dsonar.host.url=http://localhost:9001 \
        -Dsonar.token=[TOKEN]
    ```

#References

 - SonarQube: https://www.sonarsource.com/
 - SonarScanner: https://docs.sonarsource.com/sonarqube-server/10.4/analyzing-source-code/scanners/sonarscanner/
 - Github Repo: https://github.com/rukmi-patel-it/SonarQube
