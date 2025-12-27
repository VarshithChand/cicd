pipeline {
    agent any

    /*
     🔔 TRIGGER SECTION
     This enables automatic build on every GitHub push for me
    */
    triggers {
        githubPush()
    }

    stages {

        stage('Clone') {
            steps {
                git 'https://github.com/VarshithChand/cicd.git'
            }
        }

        stage('Docker Build') {
            steps {
                sh 'docker build -t varshithchand/python-app:latest .'
            }
        }

        stage('Docker Push') {
            steps {
                withCredentials([
                    usernamePassword(
                        credentialsId: 'dockerhub-creds',
                        usernameVariable: 'DOCKER_USER',
                        passwordVariable: 'DOCKER_PASS'
                    )
                ]) {
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
                docker pull varshithchand/python-app:latest
                docker run -d -p 80:5000 --name app varshithchand/python-app:latest
                '''
            }
        }
    }

    post {
        success {
            echo "✅ CI/CD Pipeline completed successfully!"
        }
        failure {
            echo "❌ CI/CD Pipeline failed. Check logs."
        }
    }
}
