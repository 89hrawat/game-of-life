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
                stdioRetention: 'FAILURES'
            )
        }
    }
}
stage('package the build') {
    steps {
               sh 'mvn clean package'
                   }
          }


stage('Archive Artifacts') {
    steps {
         archiveArtifacts(
       artifacts: '**/target/*.war',
       fingerprint: true,
       followSymlinks: false,
       allowEmptyArchive: false
       )
                   }
          }

}
}
