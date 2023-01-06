node {


 
// def docker_login = params.docker_login
// def Dockerhub_URL = params.Dockerhub_URL

stage('Checkout') {
 git credentialsId: 'github', url: 'https://github.com/vardhan6500/Demo-Java-Sonar-Maven.git'
 }


stage('Build') {
    withMaven(jdk: 'java', maven: 'maven') {
        
        println "build is running"
        sh 'mvn clean package'
    }
}
 
 /*stage('Sonar') {
  withSonarQubeEnv(credentialsId: 'DemoJavaSonarMaven') {
    sh  "mvn clean verify sonar:sonar \
  -Dsonar.projectKey=Demo-Java-Sonar-Maven \
  -Dsonar.host.url=http://3.108.66.101:9000 \
  -Dsonar.login=sqp_72fc3d8ee8b0a43f7b47d06fb335dbde8a06056e"
}
}
*/
}
