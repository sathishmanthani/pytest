pipeline {
  agent any
  stages {
    stage('build') {
      steps {
        sh '''pwd

if [ -d "pytest" ] 
then
    echo "Directory pytest exists." 
    cd pytest
    git pull origin master

else
    echo "Error: Directory /path/to/dir does not exists."
    cd pytest
    git init .
    git remote add origin https://github.com/sathishmanthani/pytest.git
    git pull origin master
fi

python -m pytest -v --cov --cov-report=xml:coverage.xml
'''
        git(url: 'https://github.com/sathishmanthani/pytest.git', branch: 'master', poll: true)
      }
    }

  }
}