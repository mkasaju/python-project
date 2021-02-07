pipeline {
    
    agent any
    
    options {
        timestamps()
    }
    
  stages {
      
    stage('Code Checkout') {
      steps {
          checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '015a9f84-759b-4c26-96d0-f189443e423a', url: 'git@github.com:mkasaju/python-project.git']]])
          
      }
    }
    
    stage('Build') {
      parallel {
        stage ('First Test') {
          steps {
            echo 'Run First Test here...'
          }
        }
        
        stage('Second Test') {
          steps {
            echo 'Run Second Test here...'
          }
        }
        
        stage('Python Test') {
            steps { 
                echo 'Run python test here...'
                sh 'python *test.py'
            }
        }
        
      }
    }
    
  }
}
