pipeline {
	agent any{
	stages {
		stage('Build') {
			steps {
				sh 'composer install'
			}
		}
		stage('Test') {
			steps {
                sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c test/phpuniy.xml tests'
            }
	}
		post {
			always {
				junit testResults: 'logs/unitreport.xml' 
			}
		}
	}
}
