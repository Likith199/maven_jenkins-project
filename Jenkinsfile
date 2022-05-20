pipeline {
    agent any
    tools { 
        maven 'Maven' 
        jdk 'java' 
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${JAVA_HOME}"
                    echo "M2_HOME = ${MAVEN_HOME}"
                ''' 
            }
        }

        stage ('Build') {
            steps {
                echo 'This is a minimal pipeline.'
            }
        }
    }
}
