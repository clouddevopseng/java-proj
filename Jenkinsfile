node() {
    stage('Donwload from git') {
    git branch: 'test', url: 'https://github.com/clouddevopseng/java-proj.git'
    }
    stage('Build the code and convert into artifact') {
    sh 'mvn package'
    }
    stage('Deployed into dev env') {
    deploy adapters: [tomcat9(credentialsId: 'dev', path: '', url: 'http://15.207.115.153:8080/')], contextPath: '/testapp-script', onFailure: false, war: '**/*.war'
    }
}
