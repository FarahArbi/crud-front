pipeline {
    agent any

    stages {
        stage('Build Angular project Docker image') {
            steps {
                echo 'Build Angular project Docker image'
                
                script {
                    // Install Docker in the Jenkins container
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
