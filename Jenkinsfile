pipeline {
     agent any
     environment{
        NEW_VERSION ='1.3.0'
        GITHUB_CREDENTIALS = credentials('githubSuri')
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
              echo "Deploying with credentials ${GITHUB_CREDENTIALS}"
                 withCredentials([
                    usernamePassword(credentials: 'githubSuri' , usernameVariable: 'USER' passwordVariable: 'PWD')
                 ]){
                      echo "deploying with userName is ${USER}"
                 }
            }
         }
          stage("install"){
           steps { 
              echo 'install the application ............'
           }
        }
      }
  }
     
