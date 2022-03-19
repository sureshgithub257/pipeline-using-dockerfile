node {
    
        stage('Checkout'){
            checkout scm
        }
        stage('Build and Execute'){
            def registry = "sureshgk257/"
            docker.withRegistry('https://registry.hub.docker.com', 'docker_cred') {

                def customImage = docker.build registry + "my-image:${BUILD_ID}"
       
                customImage.inside {
                sh 'svn --version'
                }
                customImage.push()
            }
            
            
        }
}
