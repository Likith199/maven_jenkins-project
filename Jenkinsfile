pipeline {
    agent any
    tools { 
        maven 'Maven' 
        jdk 'java' 
    }
    environment {
        EMAIL_TO = 'bharathreddyv88@gmail.com'
    }
post {
        failure {
            emailext body: 'Check console output at $BUILD_URL to view the results. \n\n ${CHANGES} \n\n -------------------------------------------------- \n${BUILD_LOG, maxLines=100, escapeHtml=false}', 
                    to: "${EMAIL_TO}", 
                    subject: 'Build failed in Jenkins: $PROJECT_NAME - #$BUILD_NUMBER'
        }
        unstable {
            emailext body: 'Check console output at $BUILD_URL to view the results. \n\n ${CHANGES} \n\n -------------------------------------------------- \n${BUILD_LOG, maxLines=100, escapeHtml=false}', 
                    to: "${EMAIL_TO}", 
                    subject: 'Unstable build in Jenkins: $PROJECT_NAME - #$BUILD_NUMBER'
        }
        changed {
            emailext body: 'Check console output at $BUILD_URL to view the results.', 
                    to: "${EMAIL_TO}", 
                    subject: 'Jenkins build is back to normal: $PROJECT_NAME - #$BUILD_NUMBER'
        }
    }
    
    stages {
         stage ('git clone') {
            steps {
                git  'https://github.com/BharathSharath/maven_jenkins-project.git' 
            }
         }
          stage ('compile') {
            steps {
                bat "mvn compil" 
            }
         }
          stage ('test') {
            steps {
                bat "mvn test" 
            }
         }
          stage ('package') {
            steps {
                bat "mvn package" 
            }
         }
          stage ('Build') {
            steps {
                bat "mvn install" 
            }
         }
    }
}
