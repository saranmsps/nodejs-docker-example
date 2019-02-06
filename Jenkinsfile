pipeline {
    agent any 
    stages {
  stage('Build') {
steps {
   echo 'Running build automation'
                sh 'npm --version'
  }
}
 stage('Build Docker Image') {
     steps {
         script {
           app = docker.build("saranmsps/node-app")
           app.inside {
                sh 'echo $(curl localhost:8080)'
}
}
}
}
  stage('Push Docker Image') {
 steps {
    script {
        docker.withRegistry('https://registry.hub.docker.com','dokerhub') {
        app.push("${env.BUILD_NUMBER}")
        app.push("latest")
       }
}
}
}
                            }
                            }
