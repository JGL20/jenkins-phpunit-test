pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				sh 'apt-get update'
                       		sh 'apt-get install -y php-cli php-mbstring unzip '     
				sh 'curl -sS https://getcomposer.org/installer|php -- --install-dir=/usr/local/bin --filename=composer'
				sh 'composer --version'
				sh 'ls -la vendor/bin'  // List contents of vendor/bin to confirm PHPUnit is there
			}
		}
		stage('Test') {
    steps {
       script {
                    // Check PHPUnit version
                    sh './vendor/bin/phpunit --version'

                    // Run tests
                    sh './vendor/bin/phpunit --log-junit logs/unitreport.xml -c tests/phpunit.xml tests'
                }
    }
}
	}
}
