node {
    def app

    stage('Clone repository') {
      

        checkout scm
    }

    stage('Build image') {
  
       app = docker.build("brandonjones085/test")
    }

    stage('Push image') {
        
        docker.withRegistry('https://hub.docker.com/', 'dockerhubcred') {
            app.push("${env.BUILD_NUMBER}")
            app.push("latest")
        }
    }
}
