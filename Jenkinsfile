node {
    try {
        stage 'Checkout repository'
        checkout scm
        
        stage 'Build & package'
        def img = docker.build('473293451041.dkr.ecr.eu-central-1.amazonaws.com/docker-demo')
        // Explicitly tag it with the registry name

        stage 'Push Docker image to ECR'
        img.push('latest')

        // this should break
        fawdawfaw
    }
    catch (e) {
        currentBuild.result = "FAILED"
        throw e
    }
}

def notifyFailed() {
    emailext(
        to: "amaldini@mobiquityinc.com",
        subject: "Jenkins pipeline failed",
        body: "See title. Also, here's the env:\n{env}",
    )
}
