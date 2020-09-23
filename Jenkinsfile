pipeline {
    agent any
    tools { 
        maven 'Maven 3.3.9' 
        jdk 'jdk8' 
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                ''' 
            }
        }
        stage ('Compile Stage') {

            steps {
                dir("project_templates/java_project_template"){
                sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                dir("project_templates/java_project_template"){
                sh 'mvn test'
                }
            }
        }
        
        stage ('Packaging Stage') {

            steps {
                dir("project_templates/java_project_template"){
                sh 'mvn package'
                }
            }
        }


        
    }
}
