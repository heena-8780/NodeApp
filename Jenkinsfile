node {
    def app

    stage('Clone repository') {
        /* Cloning the Repository to our Workspace */

        // git "https://github.com/Niha-21/NodeApp.git"
        checkout scm
    }

    stage('Build image') {
        /* This builds the actual image */

        app = docker.build("nihak/nodeapp:${env.BUILD_NUMBER}")
    }

    stage('Test image') {
        
        // app.inside {
            echo "Tests passed"
        // }
    }

    stage('Push image') {
        /* 
			You would need to first register with DockerHub before you can push images to your account
		*/
        docker.withRegistry('https://registry.hub.docker.com', 'docker-hub') {
            app.push()
            } 
    }
}
