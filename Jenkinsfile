
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
            steps { HEAD
                sh 'php -v'
                sh 'composer install --no-interaction --prefer-dist'

                sh '''
                    cp .env.example .env
                    composer install --no-interaction --prefer-dist
                    php artisan key:generate
                '''
 06eec78 (Add Laravel Jenkins pipeline)
            }
        }

        stage('Test') {
            steps {
                sh 'php artisan test'
            }
        }

        stage('Deploy') {
            steps {
<<<<<<< HEAD
                echo 'Laravel deployment configuration comes next'
=======
                echo 'Build and tests successful!'
>>>>>>> 06eec78 (Add Laravel Jenkins pipeline)
            }
        }
    }
}
