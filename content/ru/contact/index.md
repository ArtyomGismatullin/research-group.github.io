---
title: Contact
date: 2022-10-24

type: landing

sections:
  - block: Contact
    content:
      title: Contact
      text: |-
        Вы можете связаться с нами, чтобы сделать проект еще лучше.
      email: 1132226530@pfur.ru
      phone: 
      address:
        street: ул. Орджоникидзе, д.3
        city: Москва
        region: Москва
        postcode: '115419'
        country: Россия
        country_code: Ru
      coordinates:
        latitude: '55.710702'
        longitude: '37.603747'
      directions: После того, как войдете в здание, пройдите в кабинет 299
      office_hours:
        - 'Понедельник с 10:30 до 12:00'
        - 'Среда с 09:00 до 10:30'
      appointment_url: 'https://calendly.com'
      #contact_links:
      #  - icon: comments
      #    icon_pack: fas
      #    name: Discuss on Forum
      #    link: 'https://discourse.gohugo.io'
    
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
    design:
      columns: '1'

  - block: markdown
    content:
      title:
      subtitle: ''
      text:
    design:
      columns: '1'
      background:
        image: 
          filename: contact.jpg
          filters:
            brightness: 1
          parallax: false
          position: center
          size: cover
          text_color_light: true
      spacing:
        padding: ['20px', '0', '20px', '0']
      css_class: fullscreen
---
