## Hello World Web Application
2.Basic directory structure

3. |----.github/workflows
4. |----Dockerfile
5. |----app.py
6. Make the flask application run locally using python app.py. Tested the root  from the browser and got the expected response
7. .![Screenshot (1)](https://github.com/Mathimohamed/py-ci-cd/assets/151551076/67b95d13-0b63-4127-954a-5d600d37d75e)
8. ## Dockerization: Dockerize the Python application
9. Dockerfile is used to create a docker container and consists of
10. FROM python:3-slim
11. RUN mkdir -p /usr/src/app
12. WORKDIR /usr/src/app
13. COPY . /usr/src/app
14. ENV APP_ENV development
15. Run pip install flask
16. EXPOSE 8000
17. CMD ["python","python.py"]
18. 
    


