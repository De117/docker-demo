node {
    stage 'Checkout repository'
    checkout scm
    
    stage 'Build & package'
    def img = docker.build('docker-demo')

    stage 'Push Docker image to ECR'
    docker.withRegistry(
        'https://473293451041.dkr.ecr.eu-central-1.amazonaws.com'
    ) {
        img.push('latest')
    }
}
