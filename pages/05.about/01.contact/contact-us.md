---
title: Contact Us
slug: contact-us
template: form
published: false

taxonomy:
  category: about_us
  tag: [about us, contact us,academy office,academy location]

form:
  name: contact
  id: contactus

  fields:
      - name: name
        label: Name
        placeholder: Enter your name
        autocomplete: on
        type: text
        validate:
          required: true
          message: Please enter your name

      - name: email
        label: Email
        placeholder: Enter your email address
        type: email
        validate:
          required: true
          message: Please enter your email address

      - name: region
        type: select
        size: long
        classes: fancy
        label: Location
        options:
            Unknown: (Please select)
            ACT: Australia - Australian Capital Territory
            NT: Australia - Northern Territory
            QLD: Australia - Queensland
            NSW: Australia - New South Wales
            SA: Australia - South Australia
            Tas: Australia - Tasmania
            Vic: Australia - Victoria
            WA: Australia - Western Australia
            Canada: Canada
            China: China
            Fiji: Fiji
            Hong Kong: Hong Kong
            Indonesia: Indonedia
            New Zealand: New Zealand
            South Africa: South Africa
            USA: USA

      - name: message
        label: Message
        placeholder: Enter your message
        type: textarea
        validate:
          required: true
          message: Please enter your message to us.

      - name: g-recaptcha-response
        label: Captcha
        type: captcha
        recaptcha_not_validated: 'Captcha not valid!'
        validate:
          required: true

      - name: note
        type: display
        size: x-small
        markdown: true
        content: "This site is protected by reCAPTCHA and the Google
        [Privacy Policy](https://policies.google.com/privacy) and
        [Terms of Service](https://policies.google.com/terms) apply."

  buttons:
      - type: submit
        value: Send

  process:
      - email:
          to: "tim.butler@harcourts.net"
          to_name: "Harcourts Academy"
          from: "{{ form.value.email }}"
          from_name: "{{ form.value.name|e }}"
          subject: "A new contact request from harcourtsacademy.com {{ form.value.name|e }}"
          body:
            - content_type: 'text/html'
              body: "{% include 'forms/data.html.twig' %}"
            - content_type: 'text/plain'
              body: "{% include 'forms/data.txt.twig' %}"
              charset: "iso-8859-1"
      - message: Thank you for getting in touch!
      - display: thanks

---

Call our Brisbane head office on <nobr><a href="tel:+61738393100">+61 (7) 3839 3100</a></nobr> during business hours ([9am to 5pm AEST](https://time.is/Brisbane)) or contact us using the form below and we will get back to you as soon as we can.
