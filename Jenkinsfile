pipeline {
    agent any
    tools { 
        maven 'Maven' 
        jdk 'java' 
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
