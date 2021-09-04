pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''pwd
mkdir pytest
cd pytest
git init .
git remote add origin https://github.com/sathishmanthani/pytest.git
git pull origin master
python -m pytest -v
'''
        git(url: 'https://github.com/sathishmanthani/pytest.git', branch: 'master', poll: true)
      }
    }

  }
}