#!groovy

node {
    checkout(scm)
    def dockerImage = "golang:1.15.8-alpine"




    docker.image(dockerImage).inside() {
        sh "git clone https://github.com/sensu/sensu-go.git"
        dir("sensu-go") {
            sh "go build -o bin/sensu-agent ./cmd/sensu-agent"
            sh "go build -o bin/sensu-backend ./cmd/sensu-backend"
            sh "go build -o bin/sensuctl ./cmd/sensuctl"
            sh "ls -1 bin"
        }
    }
}