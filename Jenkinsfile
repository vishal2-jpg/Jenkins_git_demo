
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
                git branch: 'main',
                    url: 'https://github.com/vishal2-jpg/Jenkins_git_demo.git'

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
                sh 'test -f index.html'
                echo 'HTML test passed!'
            }
        }

        stage('Check HTML') {
            steps {
                sh 'cat index.html'
            }
        }

        stage('Package') {
            steps {
                sh 'tar -czf html-project.tar.gz index.html'
                archiveArtifacts artifacts: 'html-project.tar.gz',
                    fingerprint: true
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
