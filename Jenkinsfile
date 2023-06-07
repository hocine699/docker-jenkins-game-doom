node{
    def app
    
    stage('Clone') {
        checkout scm
    }
    
    stage ('Build Image') {
        app = docker.build("mowqa/doom")
    }
    stage ('Push Image') {
        withDockerRegistry([ credentitialsID: "DockerHubID" ]) {
            dockerImage.push()
        }
    }
    
}
