# Dockerfile: 레이어를 많이 생성한 경우
FROM python:3.8-slim

# 패키지 업데이트 (1 레이어)
RUN apt-get update

# 패키지 설치 (2 레이어)
RUN apt-get install -y python3-pip

# 디렉토리 생성 (3 레이어)
RUN mkdir /app

# 파일 복사 (4 레이어)
COPY app.py /app/

# Python 라이브러리 설치 (5 레이어)
RUN pip install flask

# 작업 디렉토리 설정 (6 레이어)
WORKDIR /app

# 실행 명령어
CMD ["python3", "app.py"]