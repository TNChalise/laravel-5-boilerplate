pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh '''rm -rf vendor/
rm -rf node_modules/
composer install
php artisan migrate
'''
          }
        }
        stage('NPM install') {
          steps {
            sh 'npm install'
          }
        }
        stage('NPM serve') {
          steps {
            sh '''npm run dev
'''
          }
        }
      }
    }
    stage('Deploy') {
      steps {
        echo 'Completed'
      }
    }
  }
}