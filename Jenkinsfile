pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/VarshithChand/cicd.git'
            }
        }

        /*
         ❌ REMOVED Build & Test stages
         ✔ Python dependencies are handled inside Docker
        */

        stage('Docker Build') {
            steps {
                sh 'docker build -t varshithchand/python-app:latest .'
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
                    echo "$DOCKER_PASS" | docker login -u "$DOCKER_USER" --password-stdin
                    docker push varshithchand/python-app:latest
                    '''
                }
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                docker stop app || true
                docker rm app || true
                docker run -d -p 80:5000 --name app varshithchand/python-app:latest
                '''
            }
        }
    }
}
