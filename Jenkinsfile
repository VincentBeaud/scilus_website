pipeline {
    agent any
    stages {
        stage ('build') {
            steps {
                sh 'hugo -D -F -b "https://scil.usherbrooke.ca" -d scil.usherbrooke.ca'
            }
        }
        stage ('deploy') {
            steps {
                sh 'rsync --delete -r "$WORKSPACE/scil.usherbrooke.ca/" jenkins@scil.usherbrooke.ca:/var/www/scil.usherbrooke.ca/'
            }
        }
    }
}
