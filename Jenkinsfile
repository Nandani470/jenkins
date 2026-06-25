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

                sh 'pwd'
                sh 'ls -R'

                echo "Current Branch: ${env.GIT_BRANCH}"

                if (env.GIT_BRANCH?.contains('main')) {
                    sh '''
                    echo "===== MAIN BRANCH ====="
                    cat main/index.txt
                    '''
                }
                else if (env.GIT_BRANCH?.contains('dev')) {
                    sh '''
                    echo "===== DEV BRANCH ====="
                    cat dev/index.txt
                    '''
                }
                else if (env.GIT_BRANCH?.contains('test')) {
                    sh '''
                    echo "===== TEST BRANCH ====="
                    cat test/index.txt
                    '''
                }
                else {
                    echo "Branch not configured."
                }
            }
        }
    }
}
```

}
