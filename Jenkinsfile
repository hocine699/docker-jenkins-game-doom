node{
    stage('Clone') {
        checkout scm
    }
    stage ('Build iamge') {
        docker.build ("hocinho699/doom")
    }
    stage ('Push') {
        sh 'docker login -u hocinho699 -p dckr_pat_RKE9TZX584T4KyDMfqmQSssLP6Y'
        sh 'docker push hocinho699/doom'
    }   
    sshPublisher(publishers: [sshPublisherDesc(configName: 'vmcible', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: 'sh /home/azureuser/deploy.sh', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '/home/azureuser', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'deploy.sh')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
}    
