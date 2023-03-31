pipeline {
    agent none
    maven '3.6.3'
    stages {
        stage('Test stage') {
            agent any
            steps {
                sh 'mvn test'
            }
        }
    }
}
