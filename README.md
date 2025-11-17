pipeline {
    agent any
    stages {
        stage('hello') {
            steps {
                echo 'Bienvenue dans le pipeline Jenkins !'
                // Récupérer le code du dépôt Git
                git branch: 'main', url: 'https://github.com/chayma-rzig/student_management.git'
            }
        }
        stage('compilation') {
            steps {
                echo 'Compilation du projet...'
                // Compilation avec Maven
                sh 'mvn clean install -DskipTests'
            }
        }
    }
}
