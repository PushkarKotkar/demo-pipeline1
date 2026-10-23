pipeline {
    agent anay
    parameters { choice(name: 'ENVIROMENT',
                        choices: ['dev', 'staging', 'production']) }
    stages {
        stages('Approve') {
            when { expression {params.ENVIROMENT == 'production' } }
            steps {input massage: 'Deploy to production?' }
        }
        stages('Deploy') {
            stseps { bat "echo Deploy to ${params.ENVIROMENT}" }
        }
    }
}
