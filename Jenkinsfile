
pipeline{

	agent any

	environment {
		DOCKERHUB_CREDENTIALS=credentials('2a7c71eb-19aa-49ef-8c15-b6383d9c4bc3')
        //ARTIFACTORY_CREDENTIALS=credentials('evsil-import-dev-jfrog')
        //IMAGE_NAME='evisl-import-image'
        //IMAGE_VERSION='evisl-import-image erl-artifactory7.eso.local/eso_evisl_importer_docker_local/evisl-dev:v1'
        /* COSIGN_PASSWORD=credentials('cosign-password')
        COSIGN_PRIVATE_KEY=credentials('cosign-private-key')
        COSIGN_PUBLIC_KEY=credentials('cosign-public-key') */
	}

	 stages {

		// stage('Build') {

		// 	steps {
		// 		sh 'docker build -t evisl-import-image .'
		// 	}
		// } 
       
       
		// stage('Tag') {

		// 	steps {
		// 		sh 'docker tag  evisl-import-image erl-artifactory7.eso.local/eso_evisl_importer_docker_local/evisl-dev:v1'
		// 	}
		// } 
       
        stage('Login') {

		 	steps {
		 		sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login https://registry.hub.docker.com -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
		 	}
		 }
       
    //    stage('sign the container image') {
    //        steps {
    //    		   //sh 'alias cosign=/usr/local/bin/cosign-linux-amd64'
    //            sh 'cosign version'
    //            sh 'cosign sign --key $COSIGN_PRIVATE_KEY erl-artifactory7.eso.local/eso_evisl_importer_docker_local/evisl-dev:v1'
    //   }
    // } 
     
    //    stage('Push to artifactory') {

	// 	 	steps {
		 	  
    //           sh 'whoami'
    //           sh 'docker push erl-artifactory7.eso.local/eso_evisl_importer_docker_local/evisl-dev:v1'
	// 	 	}
	// 	 }  
       
    //     stage('verify the container image') {
    //  		steps {
    //     		sh 'cosign version'
    //     		sh 'cosign verify --key $COSIGN_PUBLIC_KEY erl-artifactory7.eso.local/eso_evisl_importer_docker_local/evisl-dev:v1'
    //   }
    // }
       
} 


}


