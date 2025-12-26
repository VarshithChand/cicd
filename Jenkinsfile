pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/VarshithChand/cicd.git'
            }
        }

        stage('Build') {
            steps {
                sh 'pip3 install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                sh 'python3 app.py || true'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t username/python-app:latest .'
            }
        }

        stage('Docker Push') {
            steps {
                withCredentials([usernamePassword(
                    credentialsId: 'dockerhub-creds',
                    usernameVariable: 'varshithchand',
                    passwordVariable: 'Varshith150711$$'
                )]) {
                    sh '''
                    docker login -u $DOCKER_USER -p $DOCKER_PASS
                    docker push username/python-app:latest
                    '''
                }
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker stop app || true
                docker rm app || true
                docker run -d -p 80:5000 --name app username/python-app:latest
                '''
            }
        }
    }
}

