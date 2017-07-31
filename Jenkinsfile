pipeline {
  agent any
  stages {
    stage('Tool Install') {
      steps {
        tool(name: 'maven', type: 'maven')
      }
    }
    stage('Checkout') {
      steps {
        echo 'Checkout'
      }
    }
  }
}