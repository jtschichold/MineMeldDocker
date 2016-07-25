# MineMeldDocker
####Simple Dockerfile for Palo Alto Networks MineMeld

##Instructions:
* Build with the following commands:

> sudo docker build -t swannysec:MineMeld github.com/swannysec/MineMeldDocker

> sudo docker run -itd -p 8880:80 4443:443 13514 swannysec:MineMeld

* Change the admin password:

> sudo docker exec -it swannysec:MineMeld sudo htpasswd /opt/minemeld/local/config/wsgi.htpasswd admin

> sudo docker exec -it swannysec:MineMeld sudo -u minemeld /opt/minemeld/engine/current/bin/supervisorctl -c /opt/minemeld/local/supervisor/config/supervisord.conf restart minemeld-web

* The Web UI will be available on https://address:4443

