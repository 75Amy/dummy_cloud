pipeline {
    agent any
    options {
        buildDiscarder(logRotator(numToKeepStr: '5'))
    }
    stages {
        stage('Scan') {
            steps {
                withSonarQubeEnv(installationName: 'sq1') {
                    ./mvnw clean org.sonarsource.scanner.maven:sonar-maven-plugin:2.16.1:sonar -Dsonar.login="admin" -Dsonar.password="admin"

                }
            }
        }
    }
}
