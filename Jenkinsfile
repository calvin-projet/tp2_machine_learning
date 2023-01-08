pipeline {
    agent any

 

    environment {
        PATH = "/System;./opt/anaconda3/lib/python3.8/;/Applications/Docker.app/Contents/Resources/bin"
    }

 

    stages {
        stage('Building') {
            steps {
                git branch: 'main', url: 'https://github.com/calvin-projet/tp2_machine_learning'
            }
        }
        stage('Testing') {
            steps {
                sh 'python -m pip install Flask'
                sh 'python test_main.py'
            }
        }
        stage('Deploying') {
            steps {
                sh 'docker build -t jenkins_app .'
                sh 'docker run -d jenkins_app'
            }
        }
    }
} 
