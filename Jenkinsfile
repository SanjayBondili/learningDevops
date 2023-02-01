pipeline {
    agent { label 'JDK17' }
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
                sh '/opt/apache-maven-3.8.7/bin/mvn package'
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
