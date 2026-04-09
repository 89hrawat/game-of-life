pipeline {
 
agent { label 'JDK8' }

stages {
  stage('checkout code') {
   steps {
     git branch: 'sprint_dev1',
	 url: 'https://github.com/89hrawat/game-of-life.git'
         }
       }
  stage('verify java version') {
   steps {
         sh 'java -version'
		 }   
      }
  stage('compile') {
    steps {
	       sh 'mvn clean compile'
		   }
          }
stage('Unit Test') {
    steps {
        sh 'mvn test'
    }
    post {
        always {
            junit(
                testResults: '**/target/surefire-reports/*.xml',
                stdioRetention: ''
            )
        }
    }
}
}
}
