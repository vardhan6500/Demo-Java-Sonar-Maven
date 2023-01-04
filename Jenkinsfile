node {

def IMAGE_NAME = params.IMAGE_NAME
def TAG_NAME = params.TAG_NAME
 def TAG_NAME_Latest = params.TAG_NAME_Latest
 def Jfog_Ip = params.Jfog_Ip
 def Jfog_Port = params.Jfog_Port
 def Repository_Key = params.Repository_Key
 
// def docker_login = params.docker_login
// def Dockerhub_URL = params.Dockerhub_URL

stage('Checkout') {
 git credentialsId: 'Github', url: 'https://github.com/leenatejababu/Demo-Java-Sonar-Maven.git'
 }


stage('Build') {
    withMaven(jdk: 'JAVA', maven: 'maven') {
        
        println "build is running"
        sh 'mvn clean package'
    }
}
 
 stage('Sonar') {
withSonarQubeEnv(credentialsId: 'sonarqubemavenexample') {
   sh "mvn clean verify sonar:sonar \
  -Dsonar.projectKey=sonarqube-maven-example \
  -Dsonar.host.url=http://43.205.98.92:9000 \
  -Dsonar.login=sqp_261e2f2747156b223bb05b06135e011fa494ffd6"
       }
    }
}
