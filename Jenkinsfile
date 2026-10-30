pipeline {
  agent any
  options {
    timeout (time: 30, unit: 'MINUITES')
    timestamp()
  }
    parameters {
      string (name:'BRANCH_NAME',defaultvalue: 'main')
      choice (name: 'BUILD_ENV',deafaultvalue: 'DEV', 'STAGING', 'PROD' )
    stages {
      stage("clone repo") {
        steps {
          echo "cloning repo"
          chekout scm
        }

      
      stage("build with params") {
        steps {
          
  
