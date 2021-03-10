pipeline {
	agent any
	
    stages {
        stage('build') {
            steps {
                retry(3) {
					echo 'Hello World!'
				}
				
				timeout(time: 10, unit: 'SECONDS') {
					cat somefile.txt
				}
            }
        }
    }
}