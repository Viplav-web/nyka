pipeline {
    agent any 
    
    parameters {
        string defaultValue: 'DEV', name: 'ENV'
    }
    
    triggers {
        pollSCM '* * * * *'
    }
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                sh '/home/viplav/Documents/maven/apache-maven-3.9.6/bin/mvn install'
            }
        }
        stage('Deployment') {
            steps {
                script {
                    if (env.ENV == 'QA') {
                        sh 'cp target/nyka.war /home/viplav/Documents/maven/apache-tomcat-9.0.88/webapps'
                        echo "Deployment has been COMPLETED on QA!"
                    } else if (env.ENV == 'UAT') {
                        sh 'cp target/nyka.war /home/viplav/Documents/maven/apache-tomcat-9.0.88/webapps'
                        echo "Deployment has been done on UAT!"
                    }
                }
            }
        }
    }
}

