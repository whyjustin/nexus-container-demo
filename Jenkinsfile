pipeline {
  agent any
  tools {
    maven 'Maven 3.3.9'
    jdk 'jdk8'
  }
  stages {
    stage ('Build') {
      steps {
        sh 'mvn dependency:copy-dependencies' 
      }
    }
    stage ('Nexus Lifecycle') {
      steps {
        nexusPolicyEvaluation iqApplication: 'nexus-lifecycle-demo', iqInstanceId: 'nexus-iq', iqStage: 'build'
      }
    }
  }
}