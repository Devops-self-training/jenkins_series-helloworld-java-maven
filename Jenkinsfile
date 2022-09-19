
node {

   label 'node01'
   stage('prepare'){
      /* groovylint-disable-next-line LineLength */
      git credentialsId: 'Github-usr-pwd', url: 'https://github.com/Devops-self-training/jenkins_series-helloworld-java-maven'
   }

   stage('Build') {
      // Run the maven build
      sh "mvn build"
   }
//   stage('UT') {
//       // Run the maven build
//       if (isUnix()) {
//          sh "'${mvnHome}/bin/mvn' -Dmaven.test.failure.ignore clean test"
//       } else {
//          bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean test/)
//       }
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
