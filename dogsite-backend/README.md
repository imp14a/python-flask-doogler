# To run each microservice

This is part of a packer sample, you can find the packer build here: https://github.com/imp14a/gcp-packer-ansible-sample

## Requires
- Python 3 
- pip installation
- apt install python3.9-venv

## Create dev enviroment
```
python3 -m venv venv
. venv/bin/activate
python3 -m pip install Flask
pip freeze > requirements.txt
```

## to run
```
pip install -r requirements.txt
gunicorn --bind 0.0.0.0:5000 wsgi:app
```

## Docker build and run
```
docker image build -t dogs-ms .
# push to gcp
gcloud builds submit .
```