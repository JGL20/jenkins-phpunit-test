pipeline {
	agent any
	stages {
		   stage('Install Composer') {
            steps {
                sh 'php -r "copy(\'https://getcomposer.org/installer\', \'composer-setup.php\');"'
                sh 'php composer-setup.php'
                sh 'php -r "unlink(\'composer-setup.php\');"'
                sh 'mv composer.phar /usr/local/bin/composer'
            }
        }
		stage('Build') {
			steps {
				sh 'composer install'
			      }
			}
		stage('Test') {
		steps {
                sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
           		 }
		}
		}
		post {
			always {
				junit testResults: 'logs/unitreport.xml' 
			}
		}
	
}
