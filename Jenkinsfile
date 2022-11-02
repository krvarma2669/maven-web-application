pipeline{

agent any

tools{
maven 'maven3.8.2'

}

triggers{
pollSCM('* * * * *')
}
options{
timestamps()
buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5'))
}

stages{

              stage('Git checkout'){
                     
                  step{
                       git credentialsId: '9eeda591-43e9-4c11-bf17-a694bf07733c', url: 'https://github.com/lokesh1220/maven-web-application.git'
                      }
                 }
          }
   

post{

 success{
 emailext to: 'devopstrainingblr@gmail.com,mithuntechnologies@yahoo.com',
          subject: "Pipeline Build is over .. Build # is ..${env.BUILD_NUMBER} and Build status is.. ${currentBuild.result}.",
          body: "Pipeline Build is over .. Build # is ..${env.BUILD_NUMBER} and Build status is.. ${currentBuild.result}.",
          replyTo: 'devopstrainingblr@gmail.com'
 }
 
 failure{
 emailext to: 'k.lokesh92@gmail.com',
          subject: "Pipeline Build is over .. Build # is ..${env.BUILD_NUMBER} and Build status is.. ${currentBuild.result}.",
          body: "Pipeline Build is over .. Build # is ..${env.BUILD_NUMBER} and Build status is.. ${currentBuild.result}.",
          replyTo: 'k.lokesh92@gmail.com'
 }
 
}


}//Pipeline closing
