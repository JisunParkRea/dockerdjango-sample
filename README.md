# dockerdjango-sample

django sample project for docker environment with Dockerfile

[Dockerfile로 django 이미지 만들기 과정 링크](https://jisun-rea.tistory.com/entry/DockerDjango-Dockerfile%EB%A1%9C-Docker-Django-%EC%9D%B4%EB%AF%B8%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0-django-20-%EB%B2%84%EC%A0%84-%EC%9D%B4%EC%83%81)


## 환경

* Windows 10 HOME
* Docker Toolbox
* Docker Quickstart Terminal
* python 3.8.1
* virtualenv


## 실행

```sh
$ git clone https://github.com/JisunParkRea/dockerdjango-sample.git
$ cd dockerdjango-sample

$ virtualenv venv
$ source env/scripts/activate
(venv)$ pip install -r requirements.txt
```

```python
# dockerdjango/settings.py의 ALLOWED_HOST에 도커 가상머신 ip를 자신의 것으로 바꾸기
ALLOWED_HOSTS = [
    '127.0.0.1',
    '<YOUR_VM_IP_ADDRESS>',
]
```

```sh
(venv)docker build -t dockerdjango .
(venv)$ docker run --name dockerdjango -p 8000:8000 -d dockerdjango:latest
```



<도커 가상머신 ip>:8000에 접속