node{
    def app
    
    stage('Clone') {
        checkout scm
    }
    
    stage ('Build Image') {
        app = docker.build("doom")
    }
    stage ('Run Docker') {
        docker.image('doom').withRun('-p 8000:8000')
    }
}
