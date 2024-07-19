php /usr/local/bin/composerpipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				sh 'apt-get update'
                       		sh 'apt-get install -y php-cli php-mbstring unzip '     
				sh 'curl -sS https://getcomposer.org/installer'
				sh 'php -- --install-dir=/usr/local/bin --filename=composer'
				sh 'php /usr/local/bin/composer install'
			}
		}
		stage('Test') {
			steps {
                	   sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
            		}
		}
	}
}
