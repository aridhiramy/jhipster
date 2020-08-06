node{
    stage('SCM Checkout'){
        git 'https://github.com/aridhiramy/jhipster.git'
    }
    
    stage('Compile-uaa'){
        sh 'cd uaa-gitlab && ./mvnw -Pprod clean verify'
    }
    stage('Compile-gateway'){
        sh 'cd gateway-gitlab && ./mvnw -Pprod clean verify'
    }
}

