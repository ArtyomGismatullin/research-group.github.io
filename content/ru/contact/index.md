---
title: Contact
date: 2022-10-24

type: landing

sections:
  - block: contact
    content:
      title: Contact
      text: |-
        You can contact us to make the project even better.
      email: 1132226530@pfur.ru
      phone: 
      address:
        street: Ordzhonikidze St., 3
        city: Moscow
        region: Moscow
        postcode: '115419'
        country: Russian Federation
        country_code: Ru
      coordinates:
        latitude: '55.710702'
        longitude: '37.603747'
      directions: Enter building and find us in 299 Office
      office_hours:
        - 'Monday 10:30 to 12:00'
        - 'Wednesday 09:00 to 10:30'
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
