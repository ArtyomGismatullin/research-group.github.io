---
title: "Первое представление проекта. Теоретическое описание задачи. Описание модели."
authors:
- admin
date: "2025-03-22T00:00:00Z"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: "2025-03-22T00:00:00Z"

# Publication type.
# Accepts a single type but formatted as a YAML list (for Hugo requirements).
# Enter a publication type from the CSL standard.

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: ""

abstract: На первом этапе проекта исследуется модель колебаний одномерных цепочек частиц в рамках математического моделирования. Теоретически описаны гармоническая цепочка (линейная модель с независимыми модами, стоячими волнами и дисперсионными соотношениями) и ангармоническая цепочка (нелинейная модель задачи Ферми-Паста-Улама). В последней введён нелинейный член, приводящий к отсутствию термализации энергии и квазипериодическому поведению системы. Основная научная проблема — выявление условий перехода к тепловому равновесию, включая влияние числа частиц, величины нелинейности и начальных условий. Для анализа использовано преобразование Фурье, позволяющее изучать спектральное распределение энергии. Результаты этапа подчёркивают фундаментальное различие между линейными и нелинейными системами, а также ставят вопросы для дальнейшего исследования динамики сложных колебательных систем.

---

```markdown
# 2 Гармоническая цепочка: модель и решение

Гармоническая цепочка представляет собой простейшую одномерную модель твердого тела. Она состоит из **N** точечных частиц массой **m**, соединённых пружинами с жёсткостью **k**. Крайние частицы прикреплены к неподвижным стенкам, что даёт общее количество пружин **N + 1**, каждая длиной **d**. Частицы могут двигаться только вдоль одной оси, а их равновесные положения задаются как:  
`x_i = i·d`  
Смещения частиц от равновесия обозначаются **y_i**, причём предполагается, что **y_i << d**.

**Сила**, действующая на **i-ю частицу**, определяется разностью смещений соседних частиц:  
```
F_i = k·(y_{i+1} - y_i) - k·(y_i - y_{i-1}) = k·(y_{i+1} - 2y_i + y_{i-1})
```

**Уравнение движения** для i-й частицы:  
```
m·d²y_i/dt² = k·(y_{i+1} - 2y_i + y_{i-1}),   i = 1, ..., N
```

**Полная энергия системы**:  
```
U = (m/2) Σ (dy_i/dt)² + (k/2) Σ (y_i - y_{i-1})²
```

**Решение уравнений движения** в виде стоячих волн:  
```
y_i = [A·cos(p·x_i) + B·sin(p·x_i)]·cos(ω·t)
```
где **p** — волновое число, **ω** — частота. Граничные условия `y_0 = 0` и `y_{N+1} = 0` дают:  
```
p_l = l·π / [(N+1)·d],   l = 1, ..., N
```

**Дисперсионное соотношение**:  
```
ω_l = 2ω_0·sin(l·π / [2(N+1)]),   ω_0 = √(k/m)
```

---

# 3 Ангармоническая цепочка: задача Ферми-Паста-Улама

**Сила** в ангармонической модели:  
```
F = -k·x·(1 - α·x/d)
```
где **α


tags:
- Source Themes
featured: false

links:
- name: GitHub source
  icon: github
  icon_pack: fab
  link: https://github.com/daBorovikov/study_2024-2025_mathmod
url_pdf: https://disk.yandex.ru/i/9aYlEYLSYZ4FEw
url_code: 'https://github.com/daBorovikov/study_2024-2025_mathmod/releases/tag/v1.3.1'
#url_dataset: '#'
#url_poster: '#'
url_project: ''
url_slides: ''
url_source: 'https://disk.yandex.ru/i/1zCv4VZUZ0fr4g'
url_video: 'https://rutube.ru/video/private/3bafd7b3ae7888790f9bf919f33856d3/?p=fdtwcqBuCpg3OX7mNvfFvA'

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/s9CC2SKySJM)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects:
- internal-project

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: example
---

