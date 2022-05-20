pipeline {
    agent any
    tools { 
        maven 'Maven' 
        jdk 'java' 
    }
    stages {
         stage ('git clone') {
            steps {
                git credentialsId: 'git_credentials', url: 'https://github.com/BharathSharath/maven_jenkins-project.git' 
            }
         }
           Stage ('build'){
                steps {
                    sh "mvn compile"
                }
            }
        

        stage ('test') {
            steps {
                sh "mvn test"
            }
        }
    }
}
