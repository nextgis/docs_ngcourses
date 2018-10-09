Создание области в  GRASS GIS
=============================

Область
-------

При работе в GRASS все данные хранятся в указаном пользователем каталоге на диске (базе геоданных). В базе может лежать несколько областей, каждая область определяется:

 * системой координат;
 * охватом/ограничивающим прямоугольником (BBox).

До тех пор, пока данные не будут импортированы в область, работа с ними невозможна.red.  *На самом деле можно использовать специальные команды (`v.external` и `r.external`), которые позволяют использовать внешние данные (не требуют импорта). Но часть модулей не будет работать с внешними данными (например, модули обработки топологии).*

Импортируемые данные должны быть в соответствующей системе координат.

Т.е. если требуется работать **в нескольких системах координат**, нужно создавать **по области для каждой системы**.




Создание области через графический интерфейс
--------------------------------------------

Запустите GRASS 7 с интерфейсом wxGUI.

 .. figure:: img/wxGUI_start.png
    :name: grass_GUI_start
    :align: center


Необходимо последовательно заполнить поля:

1. Database.
2. Location.
3. Mapset (опционально).


Варианты создания области через графический интерфейс
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

 .. figure:: img/define_Location.png
    :name: grass_define_location
    :align: center



Обычно удобно задавать систему координат и охват по существующему файлу с данными.


Создание области из командной строки
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. code:: bash

    grass70 [-c | -c geofile | -c EPSG:code[:datum_trans]]
              [-e] [-text | -gui] [--config param]
              [[[<GISDBASE>/]<LOCATION_NAME>/]<MAPSET>]

    Flags:
      -h or -help or --help      print this help message
      -v or --version            show version information and exit
      -c                         create given database, location or mapset if it doesn't exist
      -e                         exit after creation of location or mapset. Only with -c flag
      -text                      use text based interface (skip welcome screen)
                                   and set as default
      -gtext                     use text based interface (show welcome screen)
                                   and set as default
      -gui                       use wxpython graphical user interface
                                   and set as default
      --config                   print GRASS configuration parameters
                                   options: arch,build,compiler,path,revision

    Parameters:
      GISDBASE                   initial database (path to GIS data)
      LOCATION_NAME              initial location
      MAPSET                     initial mapset

Пример создадим область с системой координат и пространственным охватом, совпадающим с системой координат и охватом шейпфайла `My_file.shp`:

.. code:: bash

    grass -c My_file.shp -e ~/home/GRASSDATA/MyLocation/PERMANENT

