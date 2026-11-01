pipeline {
    agent any

    options {
        timestamps()
    }

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh 'test -f index.html'
                sh 'mkdir -p build'
                sh 'cp index.html build/index.html'
            }
        }

        stage('Test') {
            steps {
                sh 'test -s build/index.html'
                sh 'grep -q "Automated Deployment Successful" build/index.html'
            }
        }

        stage('Deploy') {
            steps {
                sh 'sudo /usr/bin/install -D -m 644 build/index.html /var/www/html/index.html'
                sh 'sudo /usr/bin/systemctl reload nginx'
            }
        }
    }

    post {
        success {
            echo 'Application deployed successfully!'
        }
    }
}
