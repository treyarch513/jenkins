node {
    stage('Clone repository') {
        git credentialsId: 'github-access', url: 'https://github.com/treyarch513/jenkins.git'
    }
    stage('Build image') {
        dockerImage = docker.build("babyeagle/node-front:1.0")
    }
    stage('Push image') {
        withDockerRegistry([ credentialsId: "docker-access", url: "" ]) {
            dockerImage.push()
        }
    }
}

