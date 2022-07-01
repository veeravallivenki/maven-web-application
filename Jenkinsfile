node
{
    def mavenHome = tool name:"maven 3.8.6"
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
  /*
   stage ('uploadArtifactintonexus')
   {
       sh "${mavenHome}/bin/mvn clean deploy"
   }
   */
   stage ('DeployingappintoTomcat')
    {
       sshagent(['4ea41a33-c221-4cde-a4ea-d382d157c10c'])
        {
          sh "scp -o StrictHostKeyChecking=no target/maven-web-application.war ec2-user@ 3.109.132.198:/opt/apache-tomcat-9.0.56/webapps/" 
        } 
    }
}
