pipeline {
    agent any

 

    environment {
        PATH = "\\System;\\Applications\\Python 3.9;\\Applications\\Docker.app\\Contents\\Resources\\bin"
    }

 

    stages {
        stage('Building') {
            steps {
                git branch: 'main', url: 'https://github.com/calvin-projet/tp2_machine_learning'
            }
        }
        stage('Testing') {
            steps {
                bat 'python -m pip install Flask'
                bat 'python test_main.py'
            }
        }
        stage('Deploying') {
            steps {
                bat 'docker build -t jenkins_app .'
                bat 'docker run -d jenkins_app'
            }
        }
    }
} 
