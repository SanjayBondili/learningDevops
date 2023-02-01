pipeline {
    agent { label JDK17 }
    stages{
        stage ('scm')
        {
            steps{
                git branch : 'main',url: 'https://github.com/spring-projects/spring-petclinic.git'
        }
        }
        stage ('build')
        {
            steps{
                sh 'mvn clean package'
            }
        }
        stage ('Archive artifacts')
        {
            steps{
                junit '**/surefire-reports/*.xml'
                archiveArtifacts artifacts: '**/*.war', followSymlinks: false
            }
        }
    }
}
}
