node() {
    stage('Donwload from git') {
    git branch: 'dev', url: 'https://github.com/clouddevopseng/java-proj.git'
    }
    stage('Build the code and convert into artifact') {
    sh 'mvn package'
    }
    stage('Deployed into dev env') {
    deploy adapters: [tomcat9(credentialsId: 'dev', path: '', url: 'http://13.203.66.12:8080/')], contextPath: '/devapp-script', war: '**/*.war'
    }
}
