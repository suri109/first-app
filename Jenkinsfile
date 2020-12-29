pipeline {
     agent any
     stages {
        stage("build"){
           when {
                expression{
                     ${BRANCH_NAME} == 'main'
                }
           }
           steps {
              echo 'Building the application ............'
           }
        }
        stage("test"){
           steps{
              echo 'Testing the application ............'
           }
        }
         stage("deploy"){
            steps { 
              echo 'Deploying the application ............'
            }
         }
          stage("install"){
           steps { 
              echo 'install the application ............'
           }
        }
      }
  }
     
