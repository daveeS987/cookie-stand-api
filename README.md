# Cookie Stand API - Lab 34

## Author: Davee Sok

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
