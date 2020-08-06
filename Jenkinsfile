node { 
  stages {
    stage ('1 choice') {
      when {
                expression { choice == '1'}
            }
            steps {
                git 'https://github.com/aridhiramy/jhipster.git'
            }
    }
    stage ('2 choice') {
      when {
                expression { choice == '2'}
            }
            steps {
                sh 'cd uaa-gitlab && ./mvnw -Pprod clean verify'
            }
    }
   stage ('3 choice') {
      when {
                expression { choice == '3'}
            }
            steps {
                sh 'cd gateway-gitlab && ./mvnw -Pprod clean verify'
            }
        }
  }
}