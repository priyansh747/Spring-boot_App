pipeline{
    agent any
    stages{
        stage('Checkout'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/priyansh747/Spring-boot_App.git']]])
            }
        }
        stage('Build'){
            steps{
                echo "Building Project"
            }
        }
    }
}
