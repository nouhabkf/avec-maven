pipeline {
    agent any

    tools {
        jdk 'JDK17'      // Nom exact de ton JDK configuré
        maven 'Maven'    // Nom exact de ton Maven configuré
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/nouhabkf/avec-maven.git', branch: 'main', credentialsId: 'ID_CREDENTIAL'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Package') {
            steps {
                sh 'mvn package'
            }
        }
    }

    post {
        success {
            echo 'Build succeeded ✅'
        }
        failure {
            echo 'Build failed ❌'
        }
    }
}
