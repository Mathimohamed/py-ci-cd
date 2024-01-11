## Hello World Web Application
2.Basic directory structure

3. |----.github/workflows
4. |----Dockerfile
5. |----app.py
6. Make the flask application run locally using python app.py. Tested the root  from the browser and got the expected response
7. .![Screenshot (1)](https://github.com/Mathimohamed/py-ci-cd/assets/151551076/67b95d13-0b63-4127-954a-5d600d37d75e)
8. ## Dockerization: Dockerize the Python application
9. Dockerfile is used to create a docker container and consists of
 FROM python:3-slim
 RUN mkdir -p /usr/src/app
 WORKDIR /usr/src/app
 COPY . /usr/src/app
 ENV APP_ENV development
 Run pip install flask
 EXPOSE 8000
 CMD ["python","python.py"]
18. Used python 3.8 version and chose rc-slim in order to reduce the size of the docker images. This can help us deploy the docker image faster. Created a working directory as ‘/python-docker’. Copied only requirements.txt because docker images are built layer by layer. Whenever the bottom layer gets changed, all the layers above them are rebuilt. So, application code changes often however, dependencies won't change much. Moreover, building the dependencies takes more time during the building process. Downloading and Installation of all the required dependencies is done using the command pip3 install. The source code is copied to the container and “CMD [ "python3","app.py"]”. "python3" This is the executable or interpreter for the Python programming language. It tells Docker to use Python 3 to execute the script and "app.py" will be executed when the container starts. It is assumed to be in the current working directory or specified path within the container.
19. ## GIT-HUB ACTION WORKFLOW
20. deploy.yml is used to execute CICD pipeline stages
21. name: Python application
22. on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]
permissions:
  contents: read
jobs:
  build:

runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v3
    - name: Set up Python 3.10
      uses: actions/setup-python@v3
      with:
        python-version: "3.10"
    - name: Install dependencies

        
        
    
      run: python python.py

    


