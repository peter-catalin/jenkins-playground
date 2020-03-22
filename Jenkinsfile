pipeline {

  // Tells Jenkins what kind of environment its supposed to use for our pipeline. 
  agent { docker { image 'maven:3.3.3' } }

  // A pipeline can contain one or more stages, and each stage can have N steps.
  stages {
    stage('Building the project') {
      steps {
        sh 'mvn --version'
        sh 'echo "Starting to build your project"'
        sh 'echo "Your project is being built..."'
        sh 'echo "Yay! Successfully built"'
      }
    }

    stage('Running tests') {
      steps {
        sh 'echo "Running tests..."'
        sh '''
            echo "This is an example"
            echo "Of a multiline step"
            echo "That works beautifully"
        '''
      }
    }

    stage('Deployment') {
      steps {
        sh 'echo "Project being deployed now"'
      }
    }
  }

  // We can also declare a post section that will execute after stages run or fail.
  post {
    always {
      echo 'This will always run'
    }
    success {
      echo 'This will run only if successful'
    }
    failure {
      echo 'This will run only if failed'
    }
    unstable {
      echo 'This will run only if the run was marked as unstable'
    }
    changed {
      echo 'This will run only if the state of the Pipeline has changed'
      echo 'For example, if the Pipeline was previously failing but is now successful'
    }
  }
}