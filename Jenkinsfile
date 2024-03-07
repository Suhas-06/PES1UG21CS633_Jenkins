pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                checkout([$class: 'GitSCM',
                           branches: [[name: '*/main']],
                           userRemoteConfigs: [[url: 'https://github.com/Suhas-06/PES1UG21CS633_Jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                build 'PES1UG21CS633-1'
                sh 'g++ main/hello.cpp -o output'
            }
        }
        stage('Test') {
            steps {
                sh './output'
            }
        }
        stage('Deploy') {
            steps {
                echo 'deploy'
            }
        }
    }
    post {
        failure {
            error 'Pipeline failed'
        }
    }
}
