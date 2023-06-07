node{
    def app
    
    stage('Clone') {
        checkout scm
    }
    
    stage ('Build Image') {
        app = docker.build("mowqa/doom")
    }
    stage ('Push Image') {
        sh 'docker login -u mowqa -p dckr_pat_is0y3bHt8AoE6BLlA7sv3NaKJMI'
        sh 'docker push mowqa/doom'
        }
    }
    
}
