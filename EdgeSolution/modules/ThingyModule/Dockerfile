FROM arm32v7/python:stretch

WORKDIR /app

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get install -y libcurl4-openssl-dev python-pip libboost-python-dev python-setuptools libglib2.0-dev  && \
    rm -rf /var/lib/apt/lists/* 

COPY requirements.txt ./
RUN pip install -r requirements.txt

COPY . .

# RUN useradd -ms /bin/bash moduleuser
# USER moduleuser

CMD [ "python", "-u", "./main.py" ]