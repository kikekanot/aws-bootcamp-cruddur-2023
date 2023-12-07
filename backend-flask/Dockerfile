FROM python:3.10-slim-buster

#Inside container
#make a new floder inside the container
WORKDIR /backend-flask

# Outside --> Inside
#this contains the libraries want to install to run the app
COPY requirements.txt requirements.txt

#Inside Container
#install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside --> Inside
# . means everything in the current directory
# first period . - /backend-flask --> Outside the container
# second period . - /backend-flask --> inside the container
COPY . .

#Set environment variables (envars)
#inside the container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

#CMD (Command)

#python3 -m flask run --host="0.0.0.0" --port="4567"
CMD [ "python3", "-m", "flask", "run", "--host=0.0.0.0", "--port=4567"]

#'docker run --rm -p 4567:4567 -it backend-flask -e FRONTEND_URL -e BACKEND_URL'