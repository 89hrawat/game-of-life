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
    stage('verify mvn version') {
   steps {
         sh 'mvn -version'
                 }
      }
  stage('install') {
    steps {
	       sh 'mvn clean install'
		   }
          }
}
}
