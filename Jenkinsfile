pipeline {
   agent any
   stages {     
      stage('Docker Build') {
         steps {
            sh 'docker compose --profile postgres build'
         }
      }
      stage('Docker Push') {
         steps {
            withCredentials([usernamePassword(credentialsId: 'dockerhub', passwordVariable: 'dockerHubPassword', usernameVariable: 'dockerHubUser')]) {
               sh "docker login -u ${env.dockerHubUser} -p ${env.dockerHubPassword}"
               sh 'docker compose --profile postgres push'
            }
         }       
      }
   }
}
