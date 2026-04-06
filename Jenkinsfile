pipeline{
  agent any
  stages{
    stage('1.Checkout'){
      steps{
        git url:'https://github.com/Pranna-Nadar/docker',branch:'main'
      }
    }
    stage('2.Build Image'){
      steps{
        bat 'docker build -t mywebsite .'
      }
    }
    stage('3.Stop/Remove old Containers'){
      steps{
        bat 'docker stop mycont || exit 0'
        bat 'docker rm mycont || exit 0'
      }
    }
    stage('4. Run the Image- containerize'){
      steps{
        bat 'docker run -d -p 5000:80 --name mycont mywebsite'
  }
}
}
}

