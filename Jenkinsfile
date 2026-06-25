pipeline {
    agent any

    stages {

        stage('Display Branch Content') {
            steps {
                script {

                    def branch = env.GIT_BRANCH ?: ''

                    echo "Current Branch: ${branch}"

                    if (branch.contains('main')) {
                        sh '''
                        echo "===== MAIN BRANCH ====="
                        cat Main/index.txt
                        '''
                    }
                    else if (branch.contains('dev')) {
                        sh '''
                        echo "===== DEV BRANCH ====="
                        cat Dev/index.txt
                        '''
                    }
                    else if (branch.contains('test')) {
                        sh '''
                        echo "===== TEST BRANCH ====="
                        cat test/index.txt
                        '''
                    }
                    else {
                        echo "Branch not configured. Skipping..."
                    }
                }
            }
        }
    }
}
