pipeline {
	agent any
	
	//for using docker
	//agent {
	//	docker { image 'python:latest' }
	//}
	
	environment {
		NAME_VAR = 'Bohdan'
	}
	
    stages {
        stage('build') {
		
			environment {
				STAGE_VAR = 'Build'
			}
			
            steps {
                retry(3) {
					echo 'Hello World!'
					//sh 'python'
				}
				
				timeout(time: 1, unit: 'SECONDS') {
					echo 'Another hello world!'
					
					//it will be failed
					//cat somefile.txt
				}
				
				echo "Global variable: ${NAME_VAR}"
				echo "Build stage variable: ${STAGE_VAR}"
				
				//it will not be working
				//echo "New stage variable: ${NEW_STAGE_VAR}"
            }
        }
		
		stage('somestage') {
			
			environment {
				NEW_STAGE_VAR = 'somestage'
			}
			
			steps {
				echo "Global variable: ${NAME_VAR}"
				
				//it will not be working
				//echo "Build stage variable: ${STAGE_VAR}"
				
				echo "New stage variable: ${NEW_STAGE_VAR}"
			}
		}
    }
	
	post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}