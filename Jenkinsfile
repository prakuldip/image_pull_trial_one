pipeline {
    agent any
    environment {
        registryURI = "registry.hub.docker.com/"
        registry = "prakuldip/jenkinsfile_kul_app_trialtwo"
        registryCredential = "dockerhub_cred"
        imageTag = "b822a9dfd11973f4040263f06e0b00d6be0d7088"
    }
stages {
        stage('image pull') {
            steps{
                script {
                    docker.withRegistry("https://${registryURI}",registryCredential){
                    docker.image("${registryURI}${registry}:${imageTag}").pull()
                    }
                }
            }
        }
    }
    post { 
        always { 
            echo 'Deleting Workspace'
            deleteDir() /* clean up our workspace */
        }
    }
}