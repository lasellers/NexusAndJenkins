pipeline {
    agent any
    triggers {
        GenericTrigger(
            genericVariables: [
                [key: 'timestamp',value: '$.timestamp'],
                [key: 'nodeId',value: '$.nodeId'],
                [key: 'initiator',value: '$.initiator'],
                [key: 'action',value: '$.action'],
                [key: 'repositoryName',value: '$.repositoryName'],
                [key: 'asset_id',value: '$.asset.id'],
                [key: 'asset_assetId',value: '$.asset.assetId'],
                [key: 'asset_format',value: '$.asset.format'],
                [key: 'asset_name',value: '$.asset.name']
            ],
            
            token: 'TEST_TEST_ABC',
            causeString: 'triggered on $action',
            printContributedVariables: true,
            printPostContent: true
        )
    }
    stages {
        stage('Hello') {
            steps {
                echo 'Hello Nexus...'
                echo action
                echo repositoryName
                echo timestamp
                echo 'asset_format =' + asset_format
                echo 'asset_name =' + asset_name
                script {
                    if (asset_name.startsWith('x')) {
                        echo 'X!'
                        build 'test x'
                    } 
                    if (asset_name.startsWith('photos')) {
                        echo 'photos!'
                        build 'test photos'
                    } 
                    if (asset_name.startsWith('pics')) {
                        echo 'pics!'
                        build 'test pics'
                    } 
                }
            }
        }
    }
}
