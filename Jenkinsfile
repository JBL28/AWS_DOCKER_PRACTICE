node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    steps {
      withSonarQubeEnv('MySonarQube') {           // Jenkins > Configure System > SonarQube servers 이름
        sh '''
          chmod +x gradlew
          ./gradlew --no-daemon sonar            // 최신 태스크명: sonar
        '''
      }
    }
  }
}