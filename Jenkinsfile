pipeline {
    agent any
    environment {
        // Set environment variables if needed
        COMPOSER_HOME = '/var/jenkins_home/.composer' // Example path
    }
    stages {
        stage('Verify Composer Installation') {
            steps {
                sh 'composer --version'
            }
        }
        stage('Install Dependencies') {
            steps {
                sh 'composer install'
            }
        }
    }
}


		// stage('Test') {
		// 	steps {
  //               sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
  //           }
