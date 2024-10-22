node('appserver_3120_60')
{
def app
stage('Cloning Git')
{
    /* Lets make sure we have a repository to checkout SCM */
    
}

stage('Build-and-Tag')
{
   /*  This builds the actual image;
      * This is synonymous to docker  build on the command line */
    app = docker.build('abe6191990/car_web')
}
stage('Post-to-dockerhub')
{
    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub_credentials')
}
stage('Deploy')
{
    sh "docker-compose down"
    sh "docker-compose up -d"
}
}
