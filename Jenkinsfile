
node("maven-label"){
 def mvnHome
 stage("clone"){
   git branch: 'dev', url: 'https://github.com/vms-quip/vsm-app.git'
  mvnHome = tool name: 'maven-3.6.3', type: 'maven'
 }
  stage('Build') {
      
      if (isUnix()){ 
         sh "'${mvnHome}/bin/mvn' clean install"
      } else {
         bat(/"${mvnHome}\bin\mvn" -Dmaven.test.failure.ignore clean package/)
      }
   }
   stage('Results') {
      junit '**/target/surefire-reports/TEST-*.xml'
      archive 'target/*.jar'
   }
   

}
