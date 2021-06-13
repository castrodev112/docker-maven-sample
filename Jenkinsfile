pipeline 
{
agent any
stages

{
 stage ('scm checkout')
 { steps {
     git branch: 'master', url: 'https://github.com/castro112/docker-maven-sample'
 
 } }

 stage ('code build')
 {  steps  {  withMaven(jdk: 'JAVA_HOME', maven: 'MAVEN_HOME')
  {  sh 'mvn package' } 
  }
  }

 stage ('create docker image from Dockerfile')
 { steps { sh 'docker build -t pkw0301/samplejav:v1 .' } }


stage ('upload docker image from jenkins to docker hub')
{
    steps { 

    withDockerRegistry(credentialsId: 'DEC-DEVOPS-DOCKERHUB', url: 'https://index.docker.io/v1/') {
    sh 'docker push pkw0301/samplejav:v1'
}


     }
}

}


}
