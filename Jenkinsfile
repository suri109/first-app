pipeline {
     agent any
     environment{
        NEW_VERSION ='1.3.0'
        GITHUB_CREDENTIALS = credentials('githubSuri')
     }
     
     parameters {
	     //string(name: 'VERSION', defaultValue : '' , description: "Value of Version")
	     choice(name: 'VERSION', choices: ['1.3.0', '1.4.0', '1.5.0'], description: 'choose version of value')
             booleanParam(name: 'executeTests', defaultValue: 'true' , description: '')
	     gitParameter branchFilter: 'origin/(.*)', defaultValue: 'main', name: 'BRANCH', type: 'PT_BRANCH'
	 }
     stages {
        stage("build"){
           when {
                expression{
                     env.BRANCH_NAME == 'main' || env.BRANCH_NAME == 'suri109-patch-1'
                }
           }
           steps {
              echo 'Building the application ............'
           }
        }
        stage("test"){
            when{
                 expression{
                      //env.BRANCH_NAME == 'main'
		       params.executeTests
                 }
            }
           steps{
              echo 'Testing the application ............'
           }
        }
         stage("deploy"){
            steps { 
              echo 'Deploying the application ............'
              echo "Deploying with credentials ${GITHUB_CREDENTIALS}"
                 withCredentials([[$class: 'UsernamePasswordMultiBinding' , credentialsId: 'githubSuri' , usernameVariable: 'USER' , passwordVariable: 'PWD']
                 ]){
                      echo "deploying with userName is ${USER}"
                 }
            }
         }
          stage("install"){
           steps { 
              echo 'install the application ............'
		   echo "installing version is ${params.VERSION}"
           }
        }
      }
  }
     
