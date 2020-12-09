pipeline{
    agent{label 'master'}
    tools{maven 'M#'}
    stages {
        stage('Checkout'){
            steps{
                git branch: 'main', url: 'https://github.com/Maskg/SpringPetClinic.git'
            }
        }
        stage('Build'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('Test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('Packages'){
            steps{
                sh 'mvn package'
            }
        }
        stage('Deploy'){
            steps{
                sh 'java -jar /var/lib/jenkins/workspace/PetClinicDeclrativePipeline/target/*.jar'
            }
        }
    }
}
