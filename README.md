# Cookie Stand API - Lab 34

## Author: Davee Sok

### Collaborators

Daniel Dills, Prabin Singh, Wondwosen Tsige, Michael Ryan

## Links & Resources

Link to Api:

- [18.117.79.115:8000/admin](18.117.79.115:8000/admin)
- [18.117.79.115:8000/api/v1/cookie_stand](18.117.79.115:8000/api/v1/cookie_stand)

## Overview

Deploy app to AWS.

## Feature Tasks & Requirements

### Use API Quick Start Template

- Create a new repo cookie-stand-api that uses API Quick Start as a template.
- Modify your application using instructions in README.md found in root of repo.
  - Change things app folder to be cookie_stands
  - Go through code base looking for Thing,thing and things change to cookie-stand related names.
  - E.g. Thing model becomes CookieStand
  - E.g. ThingList becomes CookieStandList
- Pro Tip: Do a global text search looking for thing
  - Search should be case insensitive.

### Deeper CookieStand Changes

- The CookieStand model must contain

```python
location = models.CharField(max_length=256)
owner = models.ForeignKey(
    get_user_model(), on_delete=models.CASCADE, null=True, blank=True
)
description = models.TextField(default="", null=True, blank=True)
hourly_sales = models.JSONField(default=list, blank=True)
minimum_customers_per_hour = models.IntegerField(default=0)
maximum_customers_per_hour = models.IntegerField(default=0)
average_cookies_per_sale = models.FloatField(default=0)
```

### Database Deployment Requirements

- Host your Database at ElephantSQL

### Site Deployment Requirements

- Deploy Docker container to AWS or Heroku

---

### My Notes

- sudo yum update
- sudo yum install git
- clone repo (Be sure to select HTTPS)
- sudo yum install -y docker
- sudo usermod -a -G docker ec2-user
- sudo curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
- sudo chmod +x /usr/local/bin/docker-compose
- sudo service docker start
- sudo chkconfig docker on
- sudo rm /etc/localtime
- sudo docker swarm init
- sudo ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
- sudo reboot
- Add missing .env
- Update allowed_hosts with EC2 IP
- Change Debug to False if not already done.

Test the Public IP on port 8000
