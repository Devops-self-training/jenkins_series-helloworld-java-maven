
pipeline {
   agent {
    label 'node01'
   }
   def mvnHome
   
   stages{
      stage('prepare'){
      /* groovylint-disable-next-line LineLength */
      steps{
         git credentialsId: 'Github-usr-pwd', url: 'https://github.com/Devops-self-training/jenkins_series-helloworld-java-maven'

         mvnHome = tool 'maven'
      }


     stage('Build') {
      // Run the maven build
      if (isUnix()) {
         sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean compile"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean compile/)
      }
   } 

  stage('UT') {
      // Run the maven build
      if (isUnix()) {
         steps{
            sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean test"
         }
      } else {
        steps{
          bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean test/)
        }
      }
//    }
//      stage('Pack') {
//       // Run the maven build
//       if (isUnix()) {
//          sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean package"
//       } else {
//          bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
//       }
//    }
//    stage('Results') {
//       junit '**/target/surefire-reports/TEST-*.xml'
//       archive 'target/*.jar'
//    }
   }
}
