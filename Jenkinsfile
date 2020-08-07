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
                sh 'cd uaa-gitlab && ./mvnw package -Pprod -DskipTests jib:dockerBuild && docker image tag uaa 172.16.23.89:5000/uaa:2.0 && docker push 172.16.23.89:5000/uaa:2.0'  
            }
        } 
   stage ('Packaging GATEWAY MS') {
      when {
                expression { choice == 'Packaging GATEWAY MS'}
            }
            steps {
                sh 'cd gateway-gitlab && ./mvnw package -Pprod -DskipTests jib:dockerBuild && docker image tag gateway 172.16.23.89:5000/gateway:2.0 && docker push 172.16.23.89:5000/gateway:2.0'
            }
        }
   stage ('Generate K8s Deployment') {
      when {
                expression { choice == 'Generate K8s Deployment'}
            }
            steps {
                sh 'jhipster import-jdl k8s-deployment.jdl'
            }
        }

  }
}