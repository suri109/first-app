pipeline {
     agent any
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
                      env.BRANCH_NAME == 'main'
                 }
            }
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
     
