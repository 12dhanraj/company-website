
pipeline
{
    agent any
    stages
    {
    stage('Stop old Container'){
    steps
      {
        bat 'docker rm -f company-website || exit 0'
      }
    }
    stage('Checkout Code')
    {
        steps
        {
            echo 'Pulling code from Github'
            checkout scm
        }
    
    }
    stage('Build Docker Image')
    {
        steps
        {
            echo 'Building Docker Image'
            bat 'Dockerbuild -t xompany-website .'
        }
    
    }
    stage('Run Docker Container')
    {
        steps
        {
            echo 'Running Docker Container'
            bat 'docker run -d -p 8070:80 company-website'
        }
    
    }
}
}

