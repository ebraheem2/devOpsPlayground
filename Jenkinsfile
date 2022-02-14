pipeline {
    agent any

    stages {
        stage('Build Web Server') {
            steps {
                echo 'Building..'
                sh '''
                cd simple_webserver
                docker build -t docker_webserver .
                docker run -p 5000:5000 docker_webserver


                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}