
pipeline{

	agent any

	// environment {
	// 	//DOCKERHUB_CREDENTIALS=credentials('access-toke-docker-hub')
    //     //ARTIFACTORY_CREDENTIALS=credentials('evsil-import-dev-jfrog')
    //     //IMAGE_NAME='evisl-import-image'
    //     //IMAGE_VERSION='evisl-import-image erl-artifactory7.eso.local/eso_evisl_importer_docker_local/evisl-dev:v1'
    //     /* COSIGN_PASSWORD=credentials('cosign-password')
    //     COSIGN_PRIVATE_KEY=credentials('cosign-private-key')
    //     COSIGN_PUBLIC_KEY=credentials('cosign-public-key') */
	// }

	 stages {

		 stage('Build') {

		 	steps {
		 		sh '''
                cd $WORKSPACE/users-api
                docker build -t user-api .
                cd $WORKSPACE/auth-api
                docker build -t auth-api .
                cd $WORKSPACE/tasks-api
                docker build -t tasks-api .
                
                '''
		 	}
		 } 
       
       
		// stage('Tag') {

		// 	steps {
		// 		sh 'docker tag  evisl-import-image erl-artifactory7.eso.local/eso_evisl_importer_docker_local/evisl-dev:v1'
		// 	}
		// } 
        // stage('Initialize'){
        //     steps {
		//  	    def dockerHome = tool 'mydocker'
        //         env.PATH = "${dockerHome}/bin:${env.PATH}"
		//  	} }
        // stage('Login') {

		//  	steps {
		//  		sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login https://registry.hub.docker.com -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
		//  	}
		//  }

         stage('Pushing Image') {
            environment {
               registryCredential = 'access-toke-docker-hub'
           }
            steps{
               script {
                 docker.withRegistry( 'https://registry.hub.docker.com', registryCredential ) {
                   docker push hamzanasir443/example-esolutions-thesis:latest
          }
        }
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


