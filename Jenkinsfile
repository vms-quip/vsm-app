
node("maven-label"){
 def mvnHome
 stage("clone"){
   git branch: 'master', url: 'https://github.com/vms-quip/vsm-app.git'
  mvnHome = tool name: 'maven-3.6.3', type: 'maven'
  echo "$mvnHome"
 }
  stage('Build') {
      
      if (isUnix()){ 
         sh "'${mvnHome}/bin/mvn' clean deploy"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
   

}
