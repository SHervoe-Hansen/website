---
# An instance of the Contact widget.
widget: contact

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 130

title: Contact
subtitle:

content:
  # Automatically link email and phone or display as text?
  autolink: true

  # Email form provider
  form:
    provider: netlify
    formspree:
      id:
    netlify:
      # Enable CAPTCHA challenge to reduce spam?
      captcha: false

  # Contact details (edit or remove options as required)
  email: stefan@cheng.es.osaka-u.ac.jp
  phone: 
  address:
    street: 1-3 Machikaneyama-cho
    city: Toyonaka-shi
    region: Osaka
    postcode: '560-8531'
    country: Japan
    country_code: JP
  coordinates: 
    latitude: '34.804151180507205'
    longitude: '135.4554138557025'
  directions: Enter building and take the stairs to Floor 2. Walk stright to the end of the corridor.
  office_hours:
    - 'Monday-Friday 08:30 to 17:15'

design:
  columns: '2'
---
