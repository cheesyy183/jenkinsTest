pipeline {
	agent any
	
    stages {
        stage('build') {
            steps {
                retry(3) {
					echo 'Hello World!'
				}
				
				timeout(time: 1, unit: 'SECONDS') {
					echo 'Another hello world!'
				}
            }
        }
    }
}