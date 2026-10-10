pipeline{
    agent any
    stages{
        stage('Build') {
            steps {
                sh 'ls'
                sh 'tar -cvf python-app.tar  *'
            }
        }
        stage('publish artifact') {
            steps {
                echo 'publishing artifact...'
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu-home', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: 'python-app.tar')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
            }
        }
    }
}