## Hello World Web Application
2.Basic directory structure

3. |----.github/workflows
4. |----Dockerfile
5. |----app.py
6. Make the flask application run locally using python app.py. Tested the root  from the browser and got the expected response
7. .![Screenshot (1)](https://github.com/Mathimohamed/py-ci-cd/assets/151551076/67b95d13-0b63-4127-954a-5d600d37d75e)
##Dockerization: Dockerize the Python application
8.Dockerfile is used to create a docker container and consists of
FROM python:3-slim
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app
COPY . /usr/src/app
#ENV APP_ENV development
Run pip install flask 
EXPOSE 8000
CMD ["python","python.py"]


