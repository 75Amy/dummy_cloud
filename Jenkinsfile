pipeline {
    agent any
    options {
        buildDiscarder(logRotator(numToKeepStr: '5'))
    }
    stages {
        stage('Scan') {
            steps {
                withSonarQubeEnv(installationName: 'sq1') {
                    sh '/opt/sonar-scanner/bin/sonar-scanner -Dsonar.projectKey=14848project -Dsonar.login=admin -Dsonar.password=admin'

                }
            }
        }
    }
}
