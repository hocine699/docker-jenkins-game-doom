node{
    def app
    
    stage('Clone') {
        checkout scm
    }
    
    stage ('Build Image') {
        app = docker.build("doom:$BUILD_NUNBER")
    }
    stage ('Run Docker') {
        sh 'docker run -d -p 8000:8000 --name doom$BUILD_NUMBER doom:$BUILD_NUMBER
    }
    
}
