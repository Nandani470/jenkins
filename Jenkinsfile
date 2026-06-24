pipeline {
    agent any

    parameters {
        choice(
            name: 'BRANCH',
            choices: ['main', 'dev'],
            description: 'Select branch'
        )
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: params.BRANCH,
                    url: 'https://github.com/Nandani470/jenkins.git'
            }
        }

        stage('Display Content') {
            steps {
                script {
                    if (params.BRANCH == 'main') {
                        sh '''
                        echo "===== MAIN BRANCH ====="
                        cat Main/index.txt
                        '''
                    }

                    if (params.BRANCH == 'dev') {
                        sh '''
                        echo "===== DEV BRANCH ====="
                        cat Dev/index.txt
                        '''
                    }
                }
            }
        }
    }
}
