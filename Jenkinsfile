stage('Build & Unit Test'){
  sh 'mvn clean verify -DskipITs=true';
  junit '**/target/surefire-reports/TEST-*.xml'
  archive 'target/*.jar'
}

stage('Integration Testing'){
  sh 'mvn clean verify -Dsurefire.skip=true';
  junit '**/target/failsafe-reports/TEST-*.xml'
  archive 'target/*.jar'
}

stage('Static Code Analysis'){
  sh 'mvn clean verify sonar:sonar -Dsonar.projectName=example-project -Dsonar.projectKey=example-project -Dsonar.projectVersion=$BUILD_NUMBER';
}
