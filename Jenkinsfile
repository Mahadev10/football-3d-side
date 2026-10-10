pipeline{
    agent any
    stages{
        stage('Build') {
            steps {
                echo 'Building...'
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
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ubuntu-home', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '''rm -r app/
                mkdir app
                tar -xvf python-app.tar -C ./app/
                rm python-app.tar
                cd app/
                python3 -m venv myenv
                source myenv/bin/activate
                pip install -r requirements.txt
                python3 app.py''', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
                echo 'Deployment completed successfully'
            }
        }
    }
}