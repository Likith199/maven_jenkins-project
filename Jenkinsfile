pipeline {
    agent any
    tools { 
        maven 'Maven' 
        jdk 'java' 
    }
    stages {
         stage ('Build') {
            steps {
                sh 'mvn -Dmaven.test.failure.ignore=true install' 
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }

        stage ('test') {
            steps {
                echo 'This is a minimal pipeline.'
            }
        }
    }
}
