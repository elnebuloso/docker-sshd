pipeline {
    agent any

    stages {
        stage('debian7') {
            steps {
                script {
                    image = docker.build("elnebuloso/sshd:debian7", "--pull --rm --no-cache -f Dockerfile.debian7 .")
                    docker.withRegistry("https://registry.hub.docker.com", '061d45cc-bc11-4490-ac21-3b2276f1dd05'){
                        image.push()
                    }
                }
            }
        }

        stage('debian8') {
            steps {
                script {
                    image = docker.build("elnebuloso/sshd:debian8", "--pull --rm --no-cache -f Dockerfile.debian8 .")
                    docker.withRegistry("https://registry.hub.docker.com", '061d45cc-bc11-4490-ac21-3b2276f1dd05'){
                        image.push()
                    }
                }
            }
        }

        stage('debian9') {
            steps {
                script {
                    image = docker.build("elnebuloso/sshd:debian9", "--pull --rm --no-cache -f Dockerfile.debian9 .")
                    docker.withRegistry("https://registry.hub.docker.com", '061d45cc-bc11-4490-ac21-3b2276f1dd05'){
                        image.push()
                    }
                }
            }
        }

        stage('ubuntu14') {
            steps {
                script {
                    image = docker.build("elnebuloso/sshd:ubuntu14", "--pull --rm --no-cache -f Dockerfile.ubuntu14 .")
                    docker.withRegistry("https://registry.hub.docker.com", '061d45cc-bc11-4490-ac21-3b2276f1dd05'){
                        image.push()
                    }
                }
            }
        }

        stage('ubuntu16') {
            steps {
                script {
                    image = docker.build("elnebuloso/sshd:ubuntu16", "--pull --rm --no-cache -f Dockerfile.ubuntu16 .")
                    docker.withRegistry("https://registry.hub.docker.com", '061d45cc-bc11-4490-ac21-3b2276f1dd05'){
                        image.push()
                    }
                }
            }
        }

        stage('ubuntu18') {
            steps {
                script {
                    image = docker.build("elnebuloso/sshd:ubuntu18", "--pull --rm --no-cache -f Dockerfile.ubuntu18 .")
                    docker.withRegistry("https://registry.hub.docker.com", '061d45cc-bc11-4490-ac21-3b2276f1dd05'){
                        image.push()
                    }
                }
            }
        }
    }

	post {
	    always {
            cleanWs()
	    }
	}
}