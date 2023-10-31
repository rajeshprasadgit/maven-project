pipeline {
    agent any
    tools {
        maven "maven"
        }
        stages {
            stage ('SCM') {
                steps {
                    git branch: 'master', credentialsId: 'github_credentials', url: 'https://github.com/rajeshprasadgit/maven-project.git'
                }
            }
            
            stage ('Build') {
            steps {
                 sh "mvn -Dmaven.test.failure.ignore=true clean package"
                }
           }
           
            stage ('Artifacts') {
            steps {
                 archiveArtifacts 'target/*.jar'
                }
           }

        }
    }
