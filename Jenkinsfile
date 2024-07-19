pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				sh 'apt-get update'
                       		sh 'apt-get install -y php8.2-mysql php8.2-gd php8.2-curl unzip default-mysql-client nodejs npm '                                       

				sh 'composer install'
			}
		}
		stage('Test') {
			steps {
                	   sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
            		}
		}
	}
}
