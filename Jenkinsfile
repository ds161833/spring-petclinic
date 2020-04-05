pipeline {
    agent any
    tools { 
        maven 'Default MyMaven' 
        jdk 'Default MyJDK' 
    }
    stages {
        stage('Build') {
            steps {
                sh 'mvn clean'
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
        stage('Deploy') {
            steps {
                sh 'mvn package'
            }
        }
    }
    failure {
        mail (
            to: "ds1618033@gmail.com",
            subject: "Build ${currentBuild.fullDisplayName} has failed",
            body: "${env.BUILD_URL} - buiild failed"
            )
    }
}
