node{
    stage('SCM Checkout'){
        git 'git@172.16.23.101:root/namla.test.git'
    }
    
    stage('Compile-Package'){
        sh 'cd uaa-gitlab && ./mvnw -Pprod clean verify'
    }
}

