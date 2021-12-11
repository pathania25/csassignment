node {

    checkout scm

    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub') {

        def customImage = docker.build("pathania90/jenkinswithplugin")

        /* Push the container to the custom Registry */
        customImage.push()
    }
}
