pipeline{
    agent any
    stages{
        stage('Build'){
            tools{
                jdk 'jdk8'
                maven 'Maven'
            }
            steps{
                echo "Building Project"
                powershell label: '', script: 'mvn clean package -f spring-boot-samples/spring-boot-sample-atmosphere/pom.xml'
            }
        }
        stage('Archive'){
            steps{
                echo "Archived Project"
                archiveArtifacts artifacts: 'spring-boot-samples/spring-boot-sample-atmosphere/target/*.jar', followSymlinks: false
            }
        }
        stage('Publish JUnit'){
            steps{
                echo "Publishing JUnit"
                junit 'spring-boot-samples/spring-boot-sample-atmosphere/target/surefire-reports/*.xml'
            }
        }
        stage('Publish HTML'){
            steps{
                echo "Publishing HTML"
                publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: false, reportDir: 'spring-boot-samples/spring-boot-sample-atmosphere/target/site/jacoco/', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: ''])
            }
        }
    }
}
