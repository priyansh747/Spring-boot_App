pipeline{
    agent any
    stages{
        stage('Build'){
            tools{
                jdk 'jdk8'
            }
            steps{
                echo "Building Project"
                powershell label: '', script: 'mvn clean package -f spring-boot-samples/spring-boot-sample-atmosphere/pom.xml'
            }
        }
        stage('Archive'){
            steps{
                echo "Archived Project"
                archiveArtifacts artifacts: 'spring-boot-samples/spring-boot-sample-atmosphere/targets/*.jar', followSymlinks: false
            }
        }
        stage('Publish JUnit'){
            steps{
                echo "Publishing JUnit"
            }
        }
        stage('Publish HTML'){
            steps{
                echo "Publishing HTML"
            }
        }
    }
}
