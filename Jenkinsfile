pipeline {
    agent any
    tools {
        maven 'maven3'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scmGit(branches: [[name: '**']], extensions: [],
                userRemoteConfigs: [[url: 'https://github.com/chaostemptemptemp-prog/maven-package-demo.git']])
            }
        }
        stage('Package') {
            steps {
                bat 'mvn clean package'
            }
        }
        stage('Run JAR') {
            steps {
                bat 'java -cp target\\maven-package-demo-1.0.jar com.example.App'
            }
        }
    }
}