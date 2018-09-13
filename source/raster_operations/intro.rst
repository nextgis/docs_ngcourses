.. sectionauthor:: Артём Светлов <artem.svetlov@nextgis.ru>

.. _ngcourse_rasters_intro:

Введение
========

Настоящий курс предназначен для начинающих пользователей и охватывает различные
аспекты работы с растровыми слоями в NextGIS QGIS

Провайдеры бесплатных снимков
================================

1. http://earthexplorer.usgs.gov/
2. https://astrodigital.com/
3. https://libra.developmentseed.org/
4. https://docs.opendata.aws/landsat-pds/readme.html
5. http://sentinel-pds.s3-website.eu-central-1.amazonaws.com/

vrt
========
Учебные данные: 4 снимка LandsatLook с геопривязкой на одном меридиане. 

1. Взять из примера 4 снимка LandsatLook с геопривязкой.
2. Открыть в QGIS.
3. Растр --> Дополнительные --> Построить виртуальный растр. 
4. Source No data = 0
