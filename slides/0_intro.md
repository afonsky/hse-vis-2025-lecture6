# Почему не 3D?

<br>

<img src="/lion.svg" style="width: 650px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 140px; left: 0px;">Источник изображения: <a href="https://github.com/eamonnmag/Visualization-Course">Eamonn Maguire</a> </figcaption>
<v-click>

#### Обычно 3D используется только для изучения изначально трехмерной информации, например, данных медицинской визуализации...
</v-click>

---

# Проблемы с 3D

<br>
<div class="grid grid-cols-[5fr_5fr] gap-20">
<div>
<figure>
  <img src="/tumblr_o1cac0hf6f1sgh0voo1_640.png" style="width: 380px !important;">
</figure>
</div>
<div>
<figure>
  <img src="/tumblr_o2a7polFWr1sgh0voo1_640.png" style="width: 400px !important;">
</figure>
</div>
</div>
<figure>
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 20px; left: 120px;">Источники изображений:<br> <a href="http://viz.wtf/post/137826497077/eye-popping-3d-triangles">http://viz.wtf/post/137826497077/eye-popping-3d-triangles</a><br> <a href="http://viz.wtf/post/139002022202/designer-drugs-ht-ducqn">http://viz.wtf/post/139002022202/designer-drugs-ht-ducqn</a>
  </figcaption>
</figure>

---

# Проблемы с 3D

<br>
<div class="grid grid-cols-[5fr_5fr] gap-20">
<div>
<figure>
  <img src="/textbook/fig_5.1.svg" style="width: 280px !important;">
</figure>
</div>
<div>
<figure>
  <img src="/Stevens_law.svg" style="width: 300px !important;">
</figure>
</div>
</div>
<figure>
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 20px; left: 0px;">Источник изображения:
<a href="https://www.cs.ubc.ca/~tmm/vadbook/">Рис. 5.1. T. Munzner. Visualization Analysis and Design (2014)</a></figcaption>
</figure>

---

# Проблемы с 3D

* На самом деле мы не видим в 3D: мы видим в "2.05D" \*
  * информацию о плоскости изображения мы получаем достаточно быстро благодаря движениям глаз
  * информацию о глубине мы получаем от движения головы/тела (значительно медленнее)
    * стереоскопическое зрение недоступно на обычном экране и имеет свои ограничения

<br>
<div class="grid grid-cols-[5fr_3fr] gap-20">
<div>
<figure>
  <img src="/textbook/fig_6.2_1.svg" style="width: 320px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 15px; left: 0px;">Источник изображения:
<a href="https://www.cs.ubc.ca/~tmm/vadbook/">Рис. 6.2. T. Munzner. Visualization Analysis and Design (2014)</a></figcaption>
</figure>
</div>
<div>
 <figure>
  <img src="/Ware10.png" style="width: 165px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 15px; left: 0px;">* Colin Ware. Visual Thinking for Design (2008)</figcaption>
</figure> 
</div>
</div>

---

# Перекрытие скрывает информацию

* Интерактивность может помочь, но это требует времени и дополнительных услилий

<div>
<v-plotly style="height: 400px; position: relative"
:data="[{
x: Array.from({length: 20}, () => Math.random()*0.3),
y: Array.from({length: 20}, () => Math.random()*0.3),
z: Array.from({length: 20}, () => Math.random()*0.3),
type: 'scatter3d',
mode: 'markers',
marker: {color: 'red', size: 4, opacity: 0.7},
showlegend: false
},
{
x: Array.from({length: 175}, () => Math.random()*0.4+0.5),
y: Array.from({length: 175}, () => Math.random()*0.4+0.5),
z: Array.from({length: 175}, () => Math.random()*0.4+0.5),
type: 'scatter3d',
mode: 'markers',
marker: {color: 'green', size: 7, opacity: 0.7},
showlegend: false
}]"
:layout="{
   scene: {camera: {eye: {x: 1.0, y: 1.0, z:1.05}},
            xaxis: {title: 'x<sub>1</sub>', range: [0.01,1]},
            yaxis: {title: 'x<sub>2</sub>', range: [0.,1]},
            zaxis: {title: 'x<sub>3</sub>', range: [0.,1]}},
   margin: {l: 20, r:20, b:20, t:1, pad: 5},
}"
:config="{displayModeBar: false}"
:options="{}"/>
</div>

---

# Перспективные искажения

<div class="grid grid-cols-[5fr_4fr] gap-10">
<div>

* Перспективное искажение
  * мешает восприятию положения и размера
  * при нем теряются преимущества плоскости
</div>
<div>
 <figure>
  <img src="/perspective.png" style="width: 400px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 15px; left: 0px;">Источник изображения: Mukherjea et al. (1996)</figcaption>
</figure> 
</div>
</div>
<br>
<figure>
  <img src="/Zentralperspektive_zeichnen.png" style="width: 450px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: -20px; left: 500px;">Источник изображения:
<a href="https://en.wikipedia.org/wiki/File:Zentralperspektive_zeichnen.png">Гравюра неизвестного мастера (1710)</a></figcaption>
</figure>

---

# Перспективные искажения

<div class="grid grid-cols-[5fr_4fr] gap-10">
<div>

* Перспективное искажение
  * мешает восприятию положения и размера
  * при нем теряются преимущества плоскости
</div>
<div>
 <figure>
  <img src="/perspective.png" style="width: 400px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 15px; left: 0px;">Источник изображения: Mukherjea et al. (1996)</figcaption>
</figure> 
</div>
</div>

<br>
<figure>
  <img src="/Fernpunkt.png" style="width: 450px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: -20px; left: 500px;">Источник изображения:
<a href="https://commons.wikimedia.org/wiki/File:Fernpunkt.png">Гравюра неизвестного мастера (1710)</a></figcaption>
</figure>

---

# Перспективные искажения

<div class="grid grid-cols-[5fr_4fr] gap-10">
<div>
<figure>
  <img src="/3D_bar_plot.png" style="width: 450px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: -40px; left: 400px;">Источник изображения:<br>
<a href="https://root-forum.cern.ch/t/slice-draw-of-a-th2-with-thstack/26033">https://root-forum.cern.ch/t/slice-draw-of-a-th2-with-thstack/26033</a></figcaption>
</figure>
</div>
<div>
<br>

#### 3D скрывает информацию
  * Есть ли что-то за большими столбиками?
    * Мы никогда этого не узнаем 🥺
</div>
</div>

---

# Столбчатая диаграмма: 3D или 2D?

<br>

<div class="grid grid-cols-[4fr_5fr] gap-10">
<div>

* Столбцы в 3D очень трудно интерпретировать из-за:
  * перспективных искажений
  * перекрытия

* Мини-диаграммы в 2D практически всегда предпочтительнее
</div>
<div>
<figure>
  <img src="/qq20140825-72x.png" style="width: 500px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 30px; left: 150px;">Источник изображения:<br>
<a href="http://perceptualedge.com/files/GraphDesignIQ.html">http://perceptualedge.com/files/GraphDesignIQ.html</a></figcaption>
</figure>
</div>
</div>

---

# 3D или 2D в диаграммах

<br>
<div class="grid grid-cols-[4fr_5fr] gap-15">
<div>
<figure>
  <img src="/time_series_3D.png" style="width: 500px !important;">
</figure>
</div>
<div>
<figure>
  <img src="/time_series_2D.png" style="width: 500px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 40px; left: 150px;">Источник изображений:<br>
<a href="https://vanwijk.win.tue.nl/clv.pdf">Рис. 1 и 4 из статьи van Wijk and van Selow (1999)</a></figcaption>
</figure>
</div>
</div>

---

# Пример аккуратного использования 3D

<br>

<div class="grid grid-cols-[4fr_4fr_4fr_4fr] gap-1">
<div>
<figure>
  <img src="/time_series_1.png" style="width: 500px !important;">
</figure>
</div>
<div>
<figure>
  <img src="/time_series_2.png" style="width: 500px !important;">
</figure>
</div>
<div>
<figure>
  <img src="/time_series_3.png" style="width: 500px !important;">
</figure>
</div>
<div>
<figure>
  <img src="/time_series_4.png" style="width: 500px !important;">
</figure>
</div>
</div>

<br>

* Перекрывающиеся диаграммы выбираются при помощи метафоры открытия ящика
  * Интерактивность тщательно продумана, чтобы избежать трудностей,<br> связанных с **неограниченной 3D-навигацией**

<figure>
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 40px; left: 450px;">Источник изображений:
<a href="https://vanwijk.win.tue.nl/clv.pdf">Рис. 3 и 7 из статьи Lopez-Hernandez et al. (2010)</a></figcaption>
</figure>

---

# Пример аккуратного использования 3D

<br>

<figure>
  <img src="/3D_economic_growth.png" style="width: 680px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: -80px; left: 700px;">Источник изображения:<br>
<a href="https://www.nytimes.com/interactive/2015/03/19/upshot/3d-yield-curve-economic-growth.html">https://www.nytimes.com/<br>interactive/2015/03/19/upshot/<br>3d-yield-curve-economic-growth.html</a></figcaption>
</figure>

---

# Неоправданное использование 3D

<br>

* 3D уместно для трехмерных в реальности пространственных данных
* 3D требует тщательного обоснования для абстрактных данных
  * Вызывало энтузиазм в 1990-х годах, но сейчас скорее скептицизм
  * Будьте особенно осторожны с использованием 3D для визуализации<br> облака точек или графов/сетей

<br>

<figure>
  <img src="/frecon.jpg" style="width: 220px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: -80px; left: 500px;">Источник изображения:<br>
<a href="https://dl.acm.org/doi/10.5555/647341.721079">E. Frecon, WebPath - A Three-Dimensional Web History (1998)</a></figcaption>
</figure>

---

# Неоправданное использование 2D

<div class="grid grid-cols-[7fr_3fr] gap-5">
<div>

* (По сравнению с 1D = текстовыми списками)
* Подумайте, требуется ли для данных двухмерное пространственное размещение
  * особенно когда основной задачей является чтение текста
  * Размещение в виде сети или графа означает снижение плотности информации и более сложный поиск по сравнению со списками

* Преимущества перевешивают затраты, если топологическая структура/контекст важны для выполнения задачи
  * Будьте особенно осторожны с результатами поиска, коллекциями документов, онтологиями
</div>
<div>
<figure>
  <img src="/network_path.svg" style="width: 300px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 15px; left: 0px;">Источник изображения:
<a href="https://www.cs.ubc.ca/~tmm/vadbook/">T. Munzner. Visualization Analysis and Design (2014)</a></figcaption>
</figure>
<br>
<br>

<figure>
  <img src="/kisspng-electronic-circuit-electrical-network-wiring-diagr.png" style="width: 320px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 15px; left: 0px;">Источник изображения:
<a href="https://www.cleanpng.com/png-electronic-circuit-electrical-network-wiring-diagr-4649565/download-png.html">link</a></figcaption>
</figure>
</div>
</div>

---

# Анимированные визуализации

<div class="grid grid-cols-[3fr_5fr] gap-10">
<div>

<br>
<figure>
  <img src="/HiggsGammaGamma-ezgif.com-optimize.gif" style="width: 300px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: 15px; left: 0px;">Источник анимации:
<a href="https://cds.cern.ch/record/2230893">https://cds.cern.ch/record/2230893</a></figcaption>
</figure>
<br>
</div>
<div>

#### Принцип: **внешнее (визуальное) сознание эффективнее (внутренней) памяти**
  * Легко сравнивать, переводя взгляд с одного вида на другой
    * Сложнее сравнить видимый объект с воспоминаниями о том, что вы видели

* Применение принципа для анимации
  * Отлично подходит для переходов между двумя состояниями с небольшими изменениями
  * Плохо для множества состояний с многими изменениями
    * Вместо этого используйте мини-диаграммы
</div>
</div>

---

# Разрешение экрана важнее эффекта погружения

* Погружение обычно не помогает при работе с абстрактными данными
  * не требуется ощущение присутствия или стереоскопическое 3D
  * Компьютер с экраном способствует интеграции рабочего процесса
* Разрешение гораздо важнее: пиксели - самый дефицитный ресурс
* Первая волна: виртуальная реальность для абстрактных данных
* Вторая волна: AR/MR (дополненная/смешанная реальность) имеет больше перспектив

<br>
<figure>
  <img src="/AR_VR.jpg" style="width: 700px !important;">
<figcaption style="color:#b3b3b3ff; font-size: 11px; position: relative; top: -220px; left: 600px;">Источник изображения:<br>
A Design Space for Spatio-Data Coordination:<br>Tangible Interaction Devices<br> for Immersive Information Visualisation.<br>
Cordeil, Bach, Li, Elliott, and Dwyer (2017)</figcaption>
</figure>