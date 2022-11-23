node{
    def mavenHome = tool name: 'maven3.8.5'
    echo "The job name is: ${env.JOB_NAME}"
    echo "the Build number is: ${env.BUILD_NUMBER}"
    echo "the node name is: ${env.NODE_NAME}"
    
//Checkout code stage
stage('CheckoutCode'){
git branch: 'development', credentialsId: '853ef4c6-6dbe-48b4-9032-9439b2de1514', url: 'https://github.com/Praveenanuganti/maven-web-application.git'
}

//Build
stage('Build'){
sh "${mavenHome}/bin/mvn clean package"
}

 /* 
 
//Execute SonarQube Report
stage('ExecuteSonarQubeReport'){
sh "${mavenHome}/bin/mvn sonar:sonar"
}

//UploadArtifacts Into Nexus
stage('UploadArtifactsInNexus'){
sh "${mavenHome}/bin/mvn deploy"
}

//Deploy app into Tomcat Server
stage('DeployApp'){
sshagent(['3638db8e-0313-4c81-a78a-fd6fcab8dec8']) {
   sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@172.31.44.241:/opt/apache-tomcat-9.0.68/webapps/"
}

}

*/
    
}//node closing
