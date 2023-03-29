pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Building..'
          }
        }

        stage('Execute') {
          steps {
            sh ''' cd myapp
 pip install -r requirements.txt'''
          }
        }

      }
    }

    stage('Test') {
      steps {
        echo 'Testing..'
        sh '''
                cd myapp
                python3 hello.py
                python3 hello.py --name=Brad
                '''
      }
    }

    stage('Deliver') {
      steps {
        echo 'Deliver....'
        sh '''
                echo "doing delivery stuff.."
                '''
      }
    }

  }
  triggers {
    pollSCM('* * * * *')
  }
}