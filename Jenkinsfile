pipeline {
    agent {
        docker {
            // Use a Jenkins image with Docker pre-installed
            image 'jenkins/jenkins:latest'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }

    stages {
        stage('Build Angular project Docker image') {
            steps {
                echo 'Build Angular project Docker image'

                script {
                    // Build Angular project Docker image
                    def imageName = 'angular-devops'
                    sh "docker build -t $imageName ."
                    sh "docker tag $imageName faraharbi/$imageName:latest"
                    sh "docker login -u faraharbi -p dckr_pat_UUq3d58bRGZ0-L8c5S9e811Iuoo"
                    sh "docker push faraharbi/$imageName:latest"
                }
            }
        }
    }
}

