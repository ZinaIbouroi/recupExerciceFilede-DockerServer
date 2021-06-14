FROM python:3
RUN  mkdir app
WORKDIR /app/
COPY myapppython.py /app/ 
RUN  pip install flask
ENV  FLASK_APP=myapppython.py 
CMD  flask run --host=0.0.0.0
