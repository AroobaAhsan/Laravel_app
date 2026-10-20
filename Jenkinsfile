
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/AroobaAhsan/Laravel_app.git'
            }
        }

        stage('Build') {
            steps {
                sh 'php -v'
                sh 'composer install --no-interaction --prefer-dist'

                sh '''
                    cp .env.example .env
                    php artisan key:generate
                '''
            }
        }

        stage('Test') {
            steps {
                sh 'php artisan test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Build and tests successful!'
            }
        }
    }
}

