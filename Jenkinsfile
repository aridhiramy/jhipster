#node{
#    stage('SCM Checkout'){
#        git 'https://github.com/aridhiramy/jhipster.git'
#    }
#    
#    stage('Compile-uaa'){
#        sh 'cd uaa-gitlab && ./mvnw -Pprod clean verify'
#    }
#    stage('Compile-gateway'){
#        sh 'cd gateway-gitlab && ./mvnw -Pprod clean verify'
#    }
#}


pipeline {
    agent any 
  stages {
    stage ('1 choice : SCM Checkout') {
      when {
                expression { choice == '1'}
            }
            steps {
                git 'https://github.com/aridhiramy/jhipster.git'
            }
    }
    stage ('2 choice : Compile-uaa') {
      when {
                expression { choice == '2'}
            }
            steps {
                sh 'cd uaa-gitlab && ./mvnw -Pprod clean verify'
            }
    }
   stage ('3 choice : Compile-gateway') {
      when {
                expression { choice == '3'}
            }
            steps {
                sh 'cd gateway-gitlab && ./mvnw -Pprod clean verify'
            }
        }
  }
}