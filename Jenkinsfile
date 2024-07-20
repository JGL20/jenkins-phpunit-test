pipeline {
	agent any 
	stages {
		stage('Build') {
			steps {
				sh 'apt-get update'
                       		sh 'apt-get install -y php7.3'    
			

			  sh 'composer install'
					sh 'composer --version'
			}
		}
		stage('Test') {
			steps {
                	   sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
            		}
		}
	}
}
