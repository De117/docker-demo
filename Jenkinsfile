node {
    stage 'Checkout repository'
    checkout scm
    
    stage 'Build & package'
    def img = docker.build('docker-demo')
}
