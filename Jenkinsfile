pipeline 
{
agent any
stages

{
 stage ('scm checkout')
 { steps {
     git branch: 'master', url: 'https://github.com/prakashk0301/docker-maven-sample'
 
 } }

 stage ('code build')
 {  steps  {  withMaven(jdk: 'JAVA_HOME', maven: 'MAVEN_HOME')
  {  sh 'mvn package' } 
  }
  }
  
 stage ('create docker image from Dockerfile')
 { steps { sh 'docker build -t pkw0301/samplejav:v1 .' 
           sh 'docker images'} }


}


}
