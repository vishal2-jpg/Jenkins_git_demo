
pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo 'Hello from Jenkins Pipeline!'
            }
        }

        stage('Checkout') {
            steps {
                echo 'Code downloaded from GitHub'
                sh 'git log -1 --oneline'
            }
        }

        stage('Build') {
            steps {
                echo 'Building HTML application'
                sh 'ls -la'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing HTML file'
                sh 'test -f index.html'
                echo 'HTML test passed!'
            }
        }

        stage('Check HTML') {
            steps {
                echo 'Displaying HTML content'
                sh 'cat index.html'
            }
        }

        stage('Package') {
            steps {
                sh 'tar -czf html-project.tar.gz index.html'
                echo 'Package created successfully!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline succeeded!'
        }

        failure {
            echo 'Pipeline failed. Check the console output.'
        }

        always {
            echo 'Pipeline execution finished.'
        }
    }
}
