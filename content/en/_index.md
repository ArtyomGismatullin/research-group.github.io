---
# Leave the homepage title empty to use the site title
title: Research group
date: 2022-10-24
type: landing

sections:
  - block: hero
    content:
      title: |
        Research group <br>
        Chain fluctuations
      image:
        filename: welcome.jpg
      text: |
        <br>
        
        Our group in this task is invited to investigate what conditions are necessary to establish equilibrium, how the approach to equilibrium occurs, and what interesting phenomena are possible in the simplest one-dimensional case.
  
  - block: collection
    content:
      title: Latest News
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
      spacing:
        padding: ['20px', '0', '0', '0']
      css_class: fullscreen

  - block: collection
    content:
      title: Latest Preprints
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
