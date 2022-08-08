node
{
    def mavenHome = tool name:"maven3.8.6"
    stage ('checkoutcode')
   { 
     git branch: 'development', credentialsId: '0d2b4e9c-703b-4b2a-9920-c437bc1958d0', url: 'https://github.com/veeravallivenki/maven-web-application.git'
   }
   stage ('build')
   { 
     sh "${mavenHome}/bin/mvn clean package"
   }
   /*
   stage ('executesonarQube server')
   {
       sh "${mavenHome}/bin/mvn clean sonar:sonar"
   }
  
   stage ('uploadArtifactintonexus')
   {
       sh "${mavenHome}/bin/mvn clean deploy"
   }
  
   stage ('DeployingappintoTomcat')
    {
       sshagent(['ea2a794d-3067-4e09-b656-f978121620e7'])
        {
          sh "scp -o StrictHostKeyChecking=no ec2-user/javaapps/maven-web-application/target/maven-web-application.war ec2-user@43.204.148.149:/opt/apache-tomcat-9.0.64/webapps/" 
        } 
    }
    */
}
