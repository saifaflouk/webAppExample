pipeline {
    agent any
    tools {
        maven 'maven' 
    }
    stages {
        stage('Builda application') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}
