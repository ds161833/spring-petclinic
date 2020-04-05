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
                echo 'Deployed... '
            }
        }
    }
    post {
        success {
            mail to: 'ds1618033@gmail.com',
                 subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Something is wrong with ${env.BUILD_URL}"
        }
        failure {
            mail to: 'ds1618033@gmail.com',
                 subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
                 body: "Something is wrong with ${env.BUILD_URL}"
        }
    }
}
