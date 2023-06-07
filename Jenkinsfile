node{
    def app
    
    stage('Clone') {
        checkout scm
    }
    
    stage 'Build Image' {
        sh 'docker build -t doom . '
    }
    stage 'Run Docker'{
        sh 'docker run -d -p 8000:8000 --name doom doom'
    }
}
