pipeline {
    agent any

    stages {
        stage('Clone SCM') {            
            steps {
                echo 'Clone project from GH'
				git branch: 'main', credentialsId: 'github', url: 'https://github.com/Sriharipothuraju/batch6.git'
            }
        }
    {
    stages {
        stage('Build Artifact') {
            steps {
                echo 'building using mavan tool'
				sh 'mvn clean install'
            }
        }
    }
    stages {
        stage('Deploy to Tomcat server') {
            steps {
                deploy adapters: [tomcat9(credentialsId: '3f0a5925-6195-4809-b7b5-c9186d10e3f0', path: '', url: 'http://10.81.10.20:8080')], contextPath: 'face book', war: '**/*.war'
            }
        }
    }

        
        
        
}



     }
    }
