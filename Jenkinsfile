pipeline
{
agent any
stages
{

stage ('scm checkout')
{steps {  git branch: 'master', url: 'https://github.com/prakashk0301/mavenproject'   }}


stage('execute unit test framework')
{steps {withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) 
{
    sh 'mvn test'   // valitade , compile then run test
}} }

stage('generate artifact and store in local maven repository')
{steps {withMaven(globalMavenSettingsConfig: '', jdk: 'JAVA_HOME', maven: 'MAVEN_HOME', mavenSettingsConfig: '', traceability: true) 
{
    sh 'mvn clean install -DskipTests'    //skip test, it also generates artifact, clean the workspace folder
}} }

}

}