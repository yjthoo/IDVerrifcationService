#pulls dockerfile (with env and OS) from https://hub.docker.com/_/python
FROM python:3.6

# set working directory
WORKDIR /usr/src/app

# copy file from your machine into new machine's current work directory
COPY requirements.txt .

# install libraries defined in requirements.txt
RUN pip install --upgrade pip
RUN pip install --no-cache-dir -r requirements.txt

# https://stackoverflow.com/questions/55313610/importerror-libgl-so-1-cannot-open-shared-object-file-no-such-file-or-directo
RUN apt-get update ##[edited]
RUN apt-get install 'ffmpeg'\
    'libsm6'\
    'libxext6'\
    'xcb'  -y

# copy files from your machine into new machine
COPY . .

# run command in new machine
CMD ["python", "app.py"]
