pipeline {
    agent { label 'linux' }
    tools {
      maven 'Maven'
    }
    stages {
        stage('Source') {
            steps {
                sh 'mvn --version'
                sh 'git --version'
                git branch: 'main',
                    url: 'https://github.com/hovnaz/jenkins-maven-build.git'
            }
        }
        stage('Clean') {
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
                 sh 'mvn package -DskipTests'
            }
        }
    }
}
