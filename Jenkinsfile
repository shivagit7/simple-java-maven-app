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
                withMaven(
                 maven: 'maven-3.3.9'
                  {
                     // Run the maven build
                      sh "mvn clean install"
 
                  }
            //    sh 'mvn -B -DskipTests clean package'
            }
        }
    }
}
