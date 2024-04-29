pipeline {
  agent any
  tools {
    jdk "jdk17"
    maven "maven3"
  }
  stages {
    stage ('fetch') {
      steps {
        git branch: 'containers', url: 'https://github.com/adigopi49/vprofile-project.git'
      }
    }
  }
}
