# ansible_playbooks
Where I keep my ansible playbooks.

### bootstrap_webservers.yml 

This is a test nsible playbook that installs httpd, sets a index file with the servers hostname, and restarts the httpd service using a handler.

### push_code.yml

This is what i actually use to get my code to my anthonykugel.com webiste.  The playbook first pulls any new code from the upstream git repositiory.  Then it uses the manage.py Django to use the makemigrations and migrate utilites to make necessary changes to the database.  It then uses the manage.py collectstatic utility to collect any html/css/js files and puts them in the staticfiles directory (which is /var/www on the ec2 instance).  Then it cycles gunicorn and nginx.  

All i have to do is run this playbook, and all new code is automatically running in production.
