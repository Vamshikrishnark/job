node {
  stage('SCM') {
    checkout scm
  }
  stage('SonarQube Analysis') {
    def mvn = tool 'm3';
    withSonarQubeEnv('mysonar') {
      sh "${mvn}/bin/mvn clean verify sonar:sonar \
  -Dsonar.projectKey=vasu \
  -Dsonar.projectName='vasu' \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.token=sqp_db8c9f6173a0e4aea322c65d3220e782758dfb37 "
    }
  }
}
