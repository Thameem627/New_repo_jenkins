pipeline {
    agent any

    parameters {
        string(
            name: 'BRANCH_NAME',
            defaultValue: 'main',
            description: 'Enter the Git branch to build'
        )

        choice(
            name: 'BUILD_ENV',
            choices: ['dev', 'staging', 'prod'],
            description: 'Select the deployment environment'
        )
    }

    options {
        timeout(time: 30, unit: 'MINUTES')
        timestamps()
    }

    stages {

        stage('Checkout') {
            steps {
                git(
                    branch: params.BRANCH_NAME,
                    url: 'https://github.com/Thameem627/New_repo_jenkins.git'
                    
                )
            }
        }

        stage('Precheck') {
            steps {
                echo "Pipeline is targeting the ${params.BUILD_ENV} environment."
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }

    post {
        success {
            archiveArtifacts artifacts: 'target/*.jar',
                             fingerprint: true
        }

        failure {
            cleanWs()
        }
    }
}
