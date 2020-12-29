pipeline {
     agent any
     stages {
        stage("build"){
           when {
                expression{
                     env.BRANCH_NAME == 'main' || env.Branch_NAME == 'suri109-patch-1'
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
     
