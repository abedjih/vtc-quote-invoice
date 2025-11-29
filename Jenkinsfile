pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Jenkins fait déjà un checkout automatique,
                // mais ça permet d’être explicite
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh '''
                    # Exemple : installation des dépendances
                '''
            }
        }

        stage('Deploy') {
            steps {
                // On déploie le contenu du workspace vers /var/www/vtc5/gestion
                sh '''
                    rsync -av --delete \
                      --exclude=".git" \
                      --exclude="node_modules" \
                      --exclude="tests" \
                      ./ /var/www/vtc5/gestion/
                '''
            }
        }
    }
}
