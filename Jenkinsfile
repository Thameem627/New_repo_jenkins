pipeline {
  agent any
  options {
    timeout (time: 30, unit: 'MINUTES')
    timestamp()
  }
    parameters {
      string (name: 'BRANCH_NAME', defaultvalue: 'main', description: 'Enter the git branch to build' )
      choices (name: 'BUILD_ENV',deafaultvalue: 'DEV', 'STAGING', 'PROD', description: 'Select the deployment environment' )
    stages {
      stage("checkout") {
        steps {
          echo "cloning repo"
          git branch: "${params.BRANCH_NAME}",
            url: https://github.com/Thameem627/New_repo_jenkins.git
        }
      }

      
      stage("build with params") {
        steps {
          
  
