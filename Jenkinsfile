pipeline {
    agent any

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
