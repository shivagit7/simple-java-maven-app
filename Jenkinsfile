pipeline {
    agent any
  //  agent {
  //      docker {
  //          image 'maven:3-alpine'
  //          args '-v /root/.m2:/root/.m2'
  //      }
  //  }
    
    stages {
        stage('Build') {
            steps {
                withMaven( maven: 'maven-3.3.9' )
                  {
                     // Run the maven build
                      sh "mvn clean install"
 
                  }
            //    sh 'mvn -B -DskipTests clean package'
            }
        }
        
       stage('publish') {
            
       input {
                      message 'publish to s3'
                      ok 'publish'
                      parameters {
                          choice choices: ['yes, no'], description: '', name: 'publish'
                      }
        }
         steps{
             if (${publish} == 'yes') {
                echo ' yes publishing oo S3'
              } else {
                echo 'No not publishing to s3'
              }
         }   
       }  
    }
}


