node
{
    def mavenHome = tool name:"maven3.8.6"
   /*
    stage ('checkoutcode')
   { 
     git branch: 'development', credentialsId: '0d2b4e9c-703b-4b2a-9920-c437bc1958d0', url: 'https://github.com/veeravallivenki/maven-web-application.git'
   }
   stage ('build')
   { 
     sh "${mavenHome}/bin/mvn clean package"
   }
   stage ('executesonarQube server')
   {
       sh "${mavenHome}/bin/mvn clean sonar:sonar"
   }
  
   stage ('uploadArtifactintonexus')
   {
       sh "${mavenHome}/bin/mvn clean deploy"
   }
   */
   stage ('DeployingappintoTomcat')
    {
       sshagent(['46e25342-e599-44b8-9804-40a699666ccf'])
        {
          sh "scp -o StrictHostKeyChecking=no /root/javaapps/maven-web-application/target/maven-web-application.war root@13.127.56.14:/opt/apache-tomcat-9.0.64/webapps/" 
        } 
    }
}
