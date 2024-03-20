# Присоединение элементов в QGIS
*Курсивом* — названия слоёв
У меня QGIS на английском, так что в некоторых местах не уверен в переводе.

## 1. Введение \
У нас должно быть два слоя. Один — тот, к которому мы будем присоединять «*blank*». Второй — тот, который мы будем присоединять «*join*». В них обоих должны быть столбцы с уникальными характеристиками (например, OSM_ID или что-то такое).

## 2. Подготовка «*join*» \
Допустим, это у нас экселевская таблица. Если в ней есть нецелые числа, лучше их сразу подготовить, заменив запятые на точки (если это по умолчанию не выставлено в excel). После чего сохраняем как CSV файл. Обычно эксель автоматически подбирает удобный разделитель, но могут быть и проблемы. Об этом ниже. \
Сохраняем CSV куда удобно. \
!Желательно неиспользуемые столбцы, даже если они в конце, удалять полностью, а не удалять значения!

## 3. Подготовка «*blank*» \
Проверяем, чтобы столбец с уникальной характеристикой, если это число, имел числовой тип. Обычно это integer. 
![alt_text](https://github.com/a-berez/QGIS-and-other/blob/main/pics/image1.png)

## 4. Загрузка «*join*» в QGIS \
**Слой → Добавить слой → delimited text layer или ctrl/cmd+Shift+T

<p id="gdcalert2" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image2.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert3">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image2.png "image_tooltip")
 \
[1] — выбираем файл, который надо загрузить \
[2] — выбираем разделитель. Чаще всего это точка с запятой, но могут быть исключения. При выборе нужно ориентироваться на окошко предпросмотра [5] \
[3] — Нужно отметить: первая строка как заголовок, цеплять типы полей, отбрасывать пустые поля, (если не изменены запятые на точки в п.2) запятая как десятичный разделитель \
[4] — очевидно \
[5] — окно предпросмотра \


<p id="gdcalert3" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image3.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert4">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image3.png "image_tooltip")
 \
Проверив всё, нажимаем добавить и проверяем загрузилась ли таблица атрибутов.
5. **Присоединение** \
В свойствах слоя выбираем присоединение и нажимаем на плюсик. \


<p id="gdcalert4" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image4.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert5">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image4.png "image_tooltip")
 \
[1] — выбираем слой, который хотим присоединить. В данном случае «<span style="text-decoration:underline;">join</span>» \
[2] — выбираем «уникальный» столбец слоя «<span style="text-decoration:underline;">join</span>» \
[3] — выбираем «уникальный» столбец слоя «<span style="text-decoration:underline;">blank</span>». Названия столбцов не обязательно совпадают. Важно, чтобы совпадали тип данных и значения \
[4] — если необходимо, отмечаем поля, которые нужно подсоединить. Если убрать галочку, подключатся все \
[5] — если необходимо выбираем префикс названия столбцов. Если убрать галочку, он будет «названиеслоя_». \
После этого проверяем, подключились ли поля в соответствующем разделе или в атрибутивке. \
После этого лучше пересохранить слой «<span style="text-decoration:underline;">blank</span>» с добавленными полями, чтобы поля стали «родными» \


<p id="gdcalert5" ><span style="color: red; font-weight: bold">>>>>>  gd2md-html alert: inline image link here (to images/image5.png). Store image on your image server and adjust path/filename/extension if necessary. </span><br>(<a href="#">Back to top</a>)(<a href="#gdcalert6">Next alert</a>)<br><span style="color: red; font-weight: bold">>>>>> </span></p>


![alt_text](images/image5.png "image_tooltip")


Аналогично поступаем и в случае, когда нам нужно прибавить к одному векторному слою другой.
