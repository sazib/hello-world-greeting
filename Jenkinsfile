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
