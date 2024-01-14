pipeline {
    agent any

    stages {
        stage('GIT') {
            steps {
                echo 'Obtenir le projet depuis Git'
                git branch: 'main',
                url: 'https://github.com/FarahArbi/projetDevops.git'
            }
        }

        stage('Build') {
            steps {
                sh 'npm install' // Install the project dependencies
                sh 'npm run build' // Build the Angular application
            }
        }

       stage('Test') {
            steps {
                script {
                    // Run tests if applicable
                    sh 'npm run test'
                }
            }
        }
    }
}
