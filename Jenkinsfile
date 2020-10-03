
node("maven-label"){
 stage("clone"){
   git branch: 'dev', url: 'https://github.com/vms-quip/vsm-app.git'
 }
 stage("build"){
 echo 'maven build'
 }
 stage("docker"){
 echo "docker builds"
 }
 stage("push"){
 echo "docker push"
 }

}
