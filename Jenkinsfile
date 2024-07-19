pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				sh 'apt-get update'
                       		sh 'apt-get install -y php-cli php-mbstring unzip '     
				sh 'curl -sS https://getcomposer.org/installer|php -- --install-dir=/usr/local/bin --filename=composer'
				sh 'composer --version'
			}
		}
		stage('Test') {
    steps {
        script {
            // Verify PHPUnit is installed
            sh 'php --version'
            sh 'phpunit --version'

            // Run tests
            sh 'php vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
        }
    }
}
	}
}
