pipeline {
    agent any

    stages {
        stage('Checkout Repository') {
            steps {
                // Clones the exact Git repository and branch where this Jenkinsfile lives
               cleanWs()
	       checkout scm
            }
        }
        
        stage('Create Directory') {
            steps {
                // Creates a new directory named 'new_folder' inside the cloned repository workspace
                sh 'mkdir -p new_folder'
                
                // Optional: Run a list command to verify the directory was created
                sh 'ls -la'
		        sh "chmod +x file1.sh"

		        sh "./file1.sh"

            }
        }
    }
}
