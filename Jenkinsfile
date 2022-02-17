pipeline {
    agent any

    stages {
        stage('Build Web Server') {
            steps {
                echo 'Building..'
                sh '''
                aws ecr get-login-password --region us-east-1 | docker login --username AWS --password-stdin 352708296901.dkr.ecr.us-east-1.amazonaws.com
                cd simple_webserver
                docker build -t docker_webserver .
                docker tag docker_webserver:latest 352708296901.dkr.ecr.us-east-1.amazonaws.com/docker_webserver:latest
                docker push 352708296901.dkr.ecr.us-east-1.amazonaws.com/docker_webserver:latest
                echo "Thank You !!"
                '''
            }
        }
        stage('Test') {
        when{changeRequest()}
            steps {
                echo 'Testing...'
                sh'''
                exit 1
                '''
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}