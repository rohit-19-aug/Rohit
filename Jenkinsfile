pipeline {
  agent any
  tools {
    maven '3.6.3' 
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn clean package'
      }
    }
    stage ('Deploy') {
      steps {
        script {
          deploy adapters: [tomcat9(credentialsId: 'c95208da-98ba-4d2b-aaf7-5fe63b6bfa63', url: 'http://3.110.131.141:8081/')], contextPath: '', onFailure: false, war: 'target/*.war' 
        }
      }
    }
  }
  post{
        always{
            mail to: "ska78657@gmail.com",
            subject: "Build result",
            body: "success"
        }
    }
}
