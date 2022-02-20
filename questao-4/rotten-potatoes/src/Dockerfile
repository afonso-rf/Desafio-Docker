FROM python:3.9.10-slim-bullseye
RUN python3 -m pip install --upgrade pip
WORKDIR /app
COPY ./requirements.txt ./
RUN pip install -r requirements.txt
COPY . .
EXPOSE 5000

CMD ["gunicorn", "--workers=3","--bind", "0.0.0.0:5000", "-c", "config.py", "app:app"]
