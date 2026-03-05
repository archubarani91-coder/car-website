pipeline {
    agent any

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                url: 'https://github.com/archubarani91-coder/car-website.git'
            }
        }

        stage('Deploy to Apache') {
            steps {
                sh '''
                rm -rf /var/www/html/*
                cp -r * /var/www/html/
                '''
            }
        }
    }

    post {
        success {
            echo 'Website Deployed Successfully!'
        }
        failure {
            echo 'Deployment Failed'
        }
    }
}
