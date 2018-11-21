
pipeline {
    agent any
    stages {
        stage('Checkout Repositories') {
            steps {
              dir('ckan') {
                checkout resolveScm(source: [$class: 'GitSCMSource', credentialsId: '', id: '_', remote: 'https://github.com/ckan/ckan.git', traits: [[$class: 'BranchDiscoveryTrait'], [$class: 'CloneOptionTrait', extension: [depth: 5, noTags: true, reference: '', shallow: true]], [$class: 'LocalBranchTrait']]], targets: [branch,'master'])
              }
            }
        }
        stage('Static Code Analysis') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
