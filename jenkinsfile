
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
                echo 'Downloading code from GitHub'

                git branch: 'main',
                    url: 'https://github.com/vishal2-jpg/jenkins-git-demo.git'
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
                echo 'HTML file exists. Test passed!'
            }
        }

        stage('Check HTML') {
            steps {
                echo 'Checking HTML file contents'

                sh '''
                    echo "HTML file details:"
                    ls -lh index.html
                    cat index.html
                '''
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging application'
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
