# chelyabinsk_okn_map

Состав команды: 
Василиса Савинова
Даниил Фенько
Маргарита Юдченко
Римма Рыжда

Ссылка на карту: 
https://vslso.github.io/chelyabinsk_okn_map/ 

Информация о городе: 
Челябинск является административным центром Челябинской области. В нем проживает порядка 1,2 млн человек. В нем располагается 1 аэропорт, 2 железнодорожных вокзала, имеет достаточно сильные внешние связи, а также имеет 20 музеев, 67 библиотек и 13 парков и садов. Челябинск считается металлургическим городов, так как в нем концентрируется большое количество производства: металлургия, машиностроение и металлообработка, приборостроение, химическая, легкая и пищевая промышленность.
Челябинск был основан в 1736 году на месте казачьей крепости Челяба. На гербе города изображен верблюд – это знак того, что когда-то здесь проходил торговый путь из Индии. На данный момент старинные здания сохранились лишь в центре, там есть пешеходные улицы, вымощенные плиткой, а также скверы и парки. В остальном же Челябинск в основном имеет застройку советских времен, но есть также современные деловые и торговые центры, отели и высотные жилые дома. Город известен не только промышленностью, но и культурной составляющей именно благодаря исторической застройке, театрам и памятникам. Некоторыми памятниками культуры также являются старые заводы, трубы, мельницы, сохранившиеся с конца XIX - начала XX века.
Самыми главными культурными точками притяжения туристов и жителей города являются пешеходная улица Кировка, там располагается 4 памятника, более 10 скульптур, так как в городе одним из символов культуры является художник-скульптор Виталий Зайков. Также особенно известны Бульвар Славы, Площадь Революции, парк «Алое поле» и многое другое – большинство памятников культуры располагается в центре города. 

Описание используемых данных

Данные с многоквартирными домами с реформы ЖКХ, на основе которых была рассчитана средняя обеспеченность квадратными метрами в районах Челябинска и определена расчетная численность населения в каждом МКД.

Данные с объектами культурного наследия:
точечный слой- те, объекты культурного наследия, которые размещены вне зданий
полигональных слой - ОКН, которые размещены в зданиях или само здание является ОКН
слой с ансамблями

Полигональных слой  с промышленными территориями.
Слой с объектами капитального строительства и административные границы города OSM. 
Слой landuse с промышленными зонами из OSM.  

Описание основных методов 
Для начала были собраны все необходимые данные и обработаны, например, таблица с точками окн были просмотрены, отфильтрованы в питоне по совпадающим номерам, чтобы выделить ансамбли, а также почищены точки – были оставлены те, которые располагаются именно в границах населенного пункта. 
Далее в QGIS созданы отдельные слои для ансамблей, то есть точкам ансамблей были отрисованы полигоны, так как их не так много, а далее аттрибутивная таблица точек сджойнена с полигонами. Точки остальных окн были выгружены в QGIS  и соединены с полигонами зданий, то есть здания окн были выделены отдельно для определенного уровня зума. То есть в итоге получилось три слоя окн – точки, здания и ансамбли.
Данные о численности населения рассчитаны при помощи выгрузки из Реформы ЖКХ, как обычно, геокодированы, рассчитана обеспеченность по городу, а далее численность жителей в мкд, что в дальнейшем станет сеткой с численностью населения по «ячейкам». 
Файлы были подгружены в jupiter notebook, затем с помощью различных методов библиотеки folium данные были визуализированы. В результате на карте можно увидеть несколько слоев: концентрация окн (точки), численность населения по ячейкам, кластеры с численностью окн (не зданий), границы города, полигоны зданий окн, индустриальные зоны.

Сложности работы
Идентификация объектов культурного наследия – определение, какие из объектов являются ансамблями, а какие вовсе уже не существуют.
Необходимость ручной проверки геокодированных данных на этапе джойня точек окн со зданиями, так как часть точек не накладывались на полигоны, а некоторые и не должны являться зданиями – для этого была необходима ручная проверка точек. 

Сильные стороны проекта
Визуализация – нам показалось удачным отображение различных слоев на одной карте.
