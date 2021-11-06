pipeline {
    agent any

    stages {
        stage('SCM Stage') {
            steps {
                echo 'Hello Batch3'
                git 'https://github.com/wakaleo/game-of-life.git'
            }
        }
        
        stage('Artifact Build Stage') {
            steps {
                echo 'Building with maven tool'
                sh 'mvn clean install'
            }
        }
        
         stage('Delploy to tomcat stage') {
            steps {
                echo 'Deploying to lab tomcat'
                deploy adapters: [tomcat9(credentialsId: '823597d6-c142-41f8-82d9-6d4341c052bd', path: '', url: 'http://3.19.31.34:8080/')], contextPath: null, war: '**/*.war'
            }
        }
    }
}
