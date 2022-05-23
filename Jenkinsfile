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
         always {  
             echo 'This will always run'  
         }  
         success {  
             echo 'This will run only if successful'  
             mail bcc: '', body: "<b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "BUILD SUCESS: Project name -> ${env.JOB_NAME}", to: "$EMAIL_TO";
         }  
         failure {  
             mail bcc: '', body: "<b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "BUILD FAILURE: Project name -> ${env.JOB_NAME}", to: "$EMAIL_TO";  
         }  
         unstable {  
             echo 'This will run only if the run was marked as unstable' 
             mail bcc: '', body: "<b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "UNSTABLE BUILD: Project name -> ${env.JOB_NAME}", to: "$EMAIL_TO";
         }  
         changed {  
             echo 'This will run only if the state of the Pipeline has changed'  
             echo 'For example, if the Pipeline was previously failing but is now successful'  
             mail bcc: '', body: "<b>Example</b><br>Project: ${env.JOB_NAME} <br>Build Number: ${env.BUILD_NUMBER} <br> URL de build: ${env.BUILD_URL}", cc: '', charset: 'UTF-8', from: '', mimeType: 'text/html', replyTo: '', subject: "STATUS CHANGED: Project name -> ${env.JOB_NAME}", to: "$EMAIL_TO";
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
                bat "mvn compile" 
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
