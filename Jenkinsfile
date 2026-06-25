pipeline {
agent any

```
stages {

    stage('Checkout') {
        steps {
            checkout scm
        }
    }

    stage('Display Branch Content') {
        steps {
            script {

                echo "Current Branch: ${env.GIT_BRANCH}"

                sh '''
                echo "===== WORKSPACE CONTENT ====="
                pwd
                ls -R
                '''

                if (env.GIT_BRANCH?.contains('main')) {

                    sh '''
                    echo "===== MAIN BRANCH ====="
                    cat main/index.txt
                    '''

                } else if (env.GIT_BRANCH?.contains('dev')) {

                    sh '''
                    echo "===== DEV BRANCH ====="
                    cat dev/index.txt
                    '''

                } else if (env.GIT_BRANCH?.contains('test')) {

                    sh '''
                    echo "===== TEST BRANCH ====="
                    cat test/index.txt
                    '''

                } else {

                    echo "Branch not configured: ${env.GIT_BRANCH}"

                }
            }
        }
    }
}

post {
    success {
        echo 'Pipeline executed successfully!'
    }

    failure {
        echo 'Pipeline failed!'
    }
}
```

}
