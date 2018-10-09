Обзор модулей для работы с растровыми данными в GRASS GIS
=========================================================

Растровые данные
----------------

Растровые данные состоят из матрицы ячеек (или пикселов), где каждая ячейка содержит число, несущее некую информацию.

Данные делятся по типам:

 * Номинальные (несравнимы между собой);
 * Порядковые (задано отношение "больше-меньше", операция сложения/вычитания не имеет смысла);
 * Непрерывные (допустимо любое числовое значение, их можно складывать и вычитать).

Работа с текущим охватом (region)
---------------------------------

Почти все действия над растрами происходят внутри виртуального прямоугольника --- охвата. Для охвата можно настроить:

 * границы (верхнюю/нижнюю, правую/левую);
 * разрешение --- размер ячейки растра (по горизонтали и вертикали).

Примеры:

```bash
    # напечатать параметры текущего региона
    g.region -p
    # установить параметры текущего региона
    g.region res=RES t=TOP b=BOTTOM e=EAST w=WEST
    # установить параметры текущего региона по растру
    g.region rast=rasterName
    # установить охват текущего региона по вектору
    g.region vect=vectorName
    # установить параметры текущего региона
    g.region vect=vectorName res=30 -p
```

Обзор модулей обработки растровых данных
----------------------------------------

[Свыше 50 модулей для обработки изображений.](https://grass.osgeo.org/grass70/manuals/imagery.html)

[Свыше 150 модулей для обработки растровых данных:](https://grass.osgeo.org/grass70/manuals/raster.html). *На самом деле трудно посчитать сколько модулей работает с растровыми данными, упоминаемые 150 модулей относятся к классу `r.xxx` модулей.*




Класс                    |ссылка
-------------------------|-----------------------------
Импорт/экспорт           | [r.import](https://grass.osgeo.org/grass70/manuals/r.import.html), [r.in.gdal](https://grass.osgeo.org/grass70/manuals/r.in.gdal.html), [r.out.gdal](https://grass.osgeo.org/grass70/manuals/r.out.gdal.html), ...
Маскирование             | [r.mask](https://grass.osgeo.org/grass70/manuals/r.mask.html)
Алгебра карт             | [r.mapcalc](https://grass.osgeo.org/grass70/manuals/r.mapcalc.html)
Анализ соседства         | [r.neighbors](https://grass.osgeo.org/grass70/manuals/r.neighbors.html), [r.mfilter](https://grass.osgeo.org/grass70/manuals/r.mfilter.html), [r.texture](https://grass.osgeo.org/grass70/manuals/r.texture.html), ...
Стоимость движения       | [r.cost](https://grass.osgeo.org/grass70/manuals/r.cost.html), [r.drain](https://grass.osgeo.org/grass70/manuals/r.drain.html), [r.walk](https://grass.osgeo.org/grass70/manuals/r.walk.html), ...
...                      | ...


