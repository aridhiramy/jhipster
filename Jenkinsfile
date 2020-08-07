pipeline {
    agent any
stages {
    stage ('Checkout SCM') {
      when {
                expression { choice == 'Checkout SCM'}
            }
            steps {
                git 'https://github.com/aridhiramy/jhipster.git'
            }
    }
    stage ('Test & Build UAA MS') {
      when {
                expression { choice == 'Test & Build UAA MS'}
            }
            steps {
                sh 'cd uaa-gitlab && ./mvnw -Pprod clean verify'
            }
    }
   stage ('Test & Build GATEWAY MS') {
      when {
                expression { choice == 'Test & Build GATEWAY MS'}
            }
            steps {
                sh 'cd gateway-gitlab && ./mvnw -Pprod clean verify'
            }
        }
   stage ('Packaging UAA MS') {
      when {
                expression { choice == 'Packaging UAA MS'}
            }
            steps {
                sh 'cd uaa-gitlab && ./mvnw package -Pprod -DskipTests jib:dockerBuild'
            }
        } 
   stage ('Packaging GATEWAY MS') {
      when {
                expression { choice == 'Packaging GATEWAY MS'}
            }
            steps {
                sh 'cd gateway-gitlab && ./mvnw package -Pprod -DskipTests jib:dockerBuild'
            }
        }  
  }
}