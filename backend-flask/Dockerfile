FROM python:3.10-slim-buster

#Inside Container
WORKDIR /backend-flask

# Outside > Inside
COPY requirements.txt requirements.txt

#Inside Container
#Install libraries used for the app
RUN pip3 install -r requirements.txt

# Outside > Inside
# First .  >  /backend-flask (outside)
# Second . > /backend-flask (inside)
COPY . .

# Set Env Vars INSIDE and will remain set when the container is running
ENV FLASK_ENV=development

COPY cmdfile.py .

# python3 -m flask run --host=0.0.0.0 --port=4567 from cmdfile.py
CMD [ "python3", "cmdfile.py"]

