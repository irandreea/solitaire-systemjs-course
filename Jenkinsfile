
pipeline {
    agent any
    stages {
        stage('Checkout Repositories') {
            steps {
              sh "echo ${branch}"
              //dir('ckan') {
              //  checkout resolveScm(source: [$class: 'GitSCMSource', credentialsId: '', id: '_', remote: 'https://github.com/ckan/ckan.git', traits: [[$class: 'BranchDiscoveryTrait'], [$class: 'CloneOptionTrait', extension: [depth: 5, noTags: true, reference: '', shallow: true]], [$class: 'LocalBranchTrait']]], targets: [branch,'master'])
              //}
              dir ('ckan') {
                checkout resolveScm ( source: [$class: 'GitSCMSource', credentialsId: '', id: '_', remote: 'https://github.com/ckan/ckan.git', traits: [[$class: 'jenkins.plugins.git.traits.BranchDiscoveryTrait']]], targets: [branch, 'master'])
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
