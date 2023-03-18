pipeline {
    agent {
        dockerfile: true
    }


    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -f Dockerfile -t simple-web .'
            }
        }
       
        // stage('Push Docker Image') {
        //   steps {
        //         withCredentials([usernamePassword(credentialsId: 'docker-hub-creds', usernameVariable: 'DOCKER_USERNAME', passwordVariable: 'DOCKER_PASSWORD')]) {
        //             sh "docker login -u $DOCKER_USERNAME -p $DOCKER_PASSWORD"
        //             sh "docker tag $IMAGE_NAME $DOCKER_USERNAME/$IMAGE_NAME:latest"
        //             sh "docker push $IMAGE_NAME:latest"
        //         }
        //     }
        // } 
    }

    post {
        success {
            echo 'Docker image built and pushed successfully'
        }
        failure {
            echo 'Docker image build and push failed'
        }
    }
}