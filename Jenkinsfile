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
    sshPublisher(publishers: [sshPublisherDesc(configName: 'Staging', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'sh deploy.sh', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
    
}
