pipeline {
  agent any

  stages {
    stage('Build') {
      steps {
        echo "Building branch: ${env.BRANCH_NAME}"
      }
    }

    stage('Test & Deploy') {
      steps {
        script {
          if (env.CHANGE_TARGET) {
             echo "This is a PR targeting ${env.CHANGE_TARGET}"
          }
          if (env.BRANCH_NAME == 'main') {
             echo "Deploying to production"
          }
        }
      }
    }
  }
}
