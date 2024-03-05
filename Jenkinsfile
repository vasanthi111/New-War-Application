pipeline {
    agent any
    tools {
        maven 'Maven3'
    }

    stages {
        stage('Clone the Repository') {
            steps {
               git 'https://github.com/suneelprojects/New-War-Application.git'
            }
        }
        
        stage('Build the Code') {
            steps {
               sh 'mvn deploy'
            }
        }
        
        
        stage('Deploy the War file in Tomcat env') {
            steps {
               deploy adapters: [tomcat7(credentialsId: 'Tomcat_Username_password', path: '', url: 'http://13.211.111.216:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
