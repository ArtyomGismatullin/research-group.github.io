---
# Leave the homepage title empty to use the site title
title: Исследовательская группа
date: 2022-10-24
type: landing

sections:
  - block: hero
    content:
      title: |
        Исследование на тему: <br>
        Колебания цепочек
      image:
        filename: welcome.jpg
      text: |
        <br>
        
        Нашей группе в этой задаче предлагается исследовать, какие условия необходимы для установления равновесия, как происходит приближение к равновесию и какие интересные явления возможны в простейшем одномерном случае.
  
  - block: collection
    content:
      title: Последние новости
      subtitle:
      text:
      count: 5
      filters:
        author: ''
        category: ''
        exclude_featured: false
        publication_type: ''
        tag: ''
      offset: 0
      order: desc
      page_type: post
    design:
      view: card
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
          filename: coders.jpg
          filters:
            brightness: 1
          parallax: false
          position: center
          size: cover
          text_color_light: true
      spacing:
        padding: ['20px', '0', '20px', '0']
      css_class: fullscreen

  - block: collection
    content:
      title: Последние препринты
      text: ""
      count: 5
      filters:
        folders:
          - publication
        publication_type: 'article'
    design:
      view: citation
      columns: '1'

  - block: markdown
    content:
      title:
      subtitle:
      text: |
        {{% cta cta_link="./people/" cta_text="Meet the team →" %}}
    design:
      columns: '1'
---
