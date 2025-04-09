pipeline {
  agent any

  environment {
    COMPOSE_PROJECT_NAME = "sooyaa"
  }

  stages {
    stage('Checkout') {
      steps {
        git branch: 'deploy', url: 'https://github.com/kitsanaphon1/docker-compose-v.1.0.git'
      }
    }

    stage('Run docker-compose') {
      steps {
        sh '''
          docker-compose down || true
          docker-compose pull        # 👉 ดึง latest images (เผื่อมีการ push ใหม่)
          docker-compose up -d
        '''
      }
    }
  }
}
