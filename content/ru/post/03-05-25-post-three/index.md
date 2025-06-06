---
title: Отчет по третьему этапу проекта
date: 2025-05-03
url_pdf: 'https://disk.yandex.ru/i/0EzTp67-MOxFhQ'
---

В этой новости мы расскажем о выполнении третьего этапа нашего проекта.

Защита третьего этапа:

<iframe width="720" height="405" src="https://rutube.ru/play/embed/c23ce537d2aaf99c68723148891e6ccf/" frameBorder="0" allow="clipboard-write; autoplay" webkitAllowFullScreen mozallowfullscreen allowFullScreen></iframe>

<!--more-->

# Введение  
Численное моделирование колебательных цепочек остаётся ключевым инструментом в механике, физике твёрдого тела и радиофизике. В отличие от аналитических решений, применимых лишь к частным случаям (однородные или периодические цепочки), численные методы позволяют исследовать системы с произвольными параметрами.

### Метод и реализация  
В настоящей работе разработан программный комплекс на языке Julia для моделирования трёхмассивной цепочки с параметрами:  
- массы m = [1, 2, 1]  
- жёсткости пружин k = [1, 1, 1, 1]  
- начальные условия R₀ = [-0.2, 0, -0.3], V₀ = [1, -3, 0]  

Основные этапы:  
- Построение трёхдиагональной матрицы жёсткости Ω и решение задачи Ω·Aₐ = ωₐ²·Aₐ  
- Вычисление амплитуд Cₐ и фаз φₐ по начальному состоянию  
- Генерация временных рядов Xᵢ(t), Vᵢ(t) на сетке из 2¹³ точек на интервале t ∈ [0, 80]  
- Визуализация: график смещения второго звена, фазовый портрет и спектральная плотность через FFT  

### Результаты  
- На графике смещения второго тела чётко видны колебания, обусловленные суперпозицией трёх нормальных мод.  
- Спектральный анализ показал яркие пики на собственных частотах ω₁, ω₂, ω₃, что подтверждает корректность алгоритма.

### Перспективы  
Методика может быть расширена на цепочки с N > 3, с учётом демпфирования и внешних воздействий, а также применена в образовательных курсах по вычислительной физике и инженерному моделированию.  

