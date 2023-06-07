node{
    def app
    
    stage('Clone') {
        checkout scm
    }
    
    stage ('Build Image') {
        app = docker.build("mowqa/doom")
    }
    stage ('Push Image') {
        withDockerRegistry([ credentitialsID: "DockerHubID", url: "https://hub.docker.com/r/mowqa/doom" ]) {
            app.push()
        }
    }
    
}
