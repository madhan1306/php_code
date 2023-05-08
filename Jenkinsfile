
pipeline {
    agent any
    properties([
    parameters([
        gitParameter(branch: '',
                     branchFilter: 'origin/(Release.*)',
                     defaultValue: 'main',
                     description: '',
                     name: 'BRANCH',
                     quickFilterEnabled: false,
                     selectedValue: 'TOP',
                     sortMode: 'NONE',
                     tagFilter: '*',
                     type: 'PT_BRANCH')
    ])
])
    stages {
        stage('php deploy') {
            steps {
                sshPublisher(publishers: [sshPublisherDesc(configName: 'ubun.sti.com', transfers: [sshTransfer(cleanRemote: false, excludes: '', execCommand: '', execTimeout: 120000, flatten: false, makeEmptyDirs: false, noDefaultExcludes: false, patternSeparator: '[, ]+', remoteDirectory: '//var/www/html/', remoteDirectorySDF: false, removePrefix: '', sourceFiles: '**/*.php')], usePromotionTimestamp: false, useWorkspaceInPromotion: false, verbose: false)])
            }
        }
    }
}
