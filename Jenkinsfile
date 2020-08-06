node{
    stage('SCM Checkout'){
        git 'https://github.com/aridhiramy/jhipster.git'
    }
    
    stage('Compile-Package'){
        sh 'cd uaa-gitlab && ./mvnw -Pprod clean verify'
    }
}

