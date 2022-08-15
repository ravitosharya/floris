pipeline {
 
    agent any
    environment {
     NEW_VERSION = '1.0'
 }
 parameters {
     choice(name: 'VERSION', choices: ['1.0', '1.1', '1.2'], description: '')
     booleanParam(name: 'exectest', defaultValue: true, description: '')
 }
    stages {
    
       stage("Build") {
         
          steps {
             echo "Building this Application"
             echo "Building version is ${NEW_VERSION}"
          }
        }
       stage("Testing") {
        when {
         expression {
          params.exectest == true
            }
        }
          steps {
             echo "Testing this Application"
          }
        }
       stage("Deploy") {
         
          steps {
             echo "Deploying this Application"
             echo "Deployed version is ${VERSION}"
          }
        }
      }
   }
