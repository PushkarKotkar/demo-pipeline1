pipeline {
    agent anay
    parameters { choice (name: 'ENVIRONMENT',
                        choices: ['dev', 'staging', 'production']) }
    stages {
        stage ('Approve') {
            when { expression {params.ENVIRONMENT == 'production' } }
            steps {input massage: 'Deploy to production?' }
        }
        stage ('Deploy') {
            stseps { bat "echo Deploy to ${params.ENVIRONMENT}" }
        }
    }
}
