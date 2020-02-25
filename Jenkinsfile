pipeline {
   agent any
   tools {
      maven 'Maven'
   }
   stages {
       stage("build") {
                steps {
                    snDevOpsStep ()
                    echo "Building" 
                    sh 'mvn -X clean install'
                    sleep 5
                }
          post {
                always {
                    junit '**/target/surefire-reports/*.xml' 
               }
          }
       }
    
      stage("deploy") {
             steps{
                  snDevOpsStep ()
                  echo "deploy in prod"
                  echo "deploy in prod"
                  snDevOpsChange()              
              }
      }      
      
  }
}
