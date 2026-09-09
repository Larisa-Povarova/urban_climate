# Urban Climate

**Urban Climate** es una aplicación web de visualización de datos climáticos, meteorológicos y de transporte urbano en Barcelona.

El proyecto se desarrolla en el contexto del cambio climático y del efecto de isla de calor urbana. La visualización permite explorar las condiciones térmicas de diferentes zonas de la ciudad y relacionarlas con la infraestructura de transporte público.

El proyecto utiliza exclusivamente fuentes de datos abiertas y no utiliza información personal ni sensible de los ciudadanos.

## Demo

🌍 **[Mapa interactivo](https://larisa-povarova.github.io/urban_climate/)**

## Visualización

El mapa permite explorar las condiciones climáticas y meteorológicas de Barcelona mediante una cuadrícula espacial de **100 × 100 metros**.

Entre los principales indicadores utilizados se encuentran:

* **UTCI (Universal Thermal Climate Index)**;
* temperatura del aire;
* tempperatura de la superficie;
* humedad relativa.

La visualización también incorpora información sobre el transporte público:

* líneas y paradas de autobús;
* líneas y estaciones de metro;
* accesos físicos a las estaciones.

Los datos pueden consultarse para diferentes **fechas e intervalos temporales** disponibles en la aplicación.

## Fuentes de datos

### Datos climáticos

Los datos climáticos históricos proceden del **Modelo Microclimático Urbano UrbClim (Copernicus)** y se transforman en una cuadrícula espacial de 100 × 100 metros.

### Datos meteorológicos

Los datos meteorológicos proceden de estaciones de **Meteocat** e incluyen información sobre temperatura, humedad, viento y otras variables meteorológicas.

### Datos de transporte

La información sobre el transporte público procede de **TMB** e incluye datos sobre líneas, paradas de autobús, líneas y estaciones de metro y accesos físicos a las estaciones.

## Datos de la aplicación

La aplicación web utiliza archivos JSON generados durante el procesamiento de los datos.

El archivo `topology.json` contiene la información estática necesaria para la visualización.

El archivo `dates.json` contiene el listado de las fechas y de los intervalos temporales para los que ya se han generado datos.

Los datos correspondientes a cada intervalo temporal se almacenan en directorios organizados por fecha:

```text
GitHub repository
├── index.html
├── topology.json
├── dates.json
├── 2026-08-10/
│   ├── delta_0000.json
│   ├── delta_0100.json
│   └── ...
├── 2026-08-21/
│   ├── delta_0000.json
│   ├── delta_0100.json
│   ├── delta_0200.json
│   └── ...
└── ...
```

De esta forma, `dates.json` permite a la aplicación identificar las fechas y los intervalos temporales disponibles, mientras que los archivos `delta_*.json` contienen los datos correspondientes a cada intervalo temporal concreto.

## Publicación

La aplicación web se publica mediante **GitHub Pages**.

El repositorio contiene el archivo `index.html` y los archivos JSON necesarios para la visualización. La aplicación utiliza estos archivos como fuente de datos para mostrar la información climática, meteorológica y de transporte.

## Autora

**Larisa Povarova**

Trabajo de Fin de Máster (TFM)<br>
Máster en Big Data & Data Engineering<br>
[Universidad Complutense de Madrid](https://masterucm.com/master-ucm/master-big-data-y-data-engineering/)<br>
Tutores: Jorge Centeno y Alberto González<br>
Septiembre de 2026

## Fuentes

* [Modelo Microclimático Urbano UrbClim (Copernicus)](https://provide.marvin.vito.be/ftp/compressed_daily/)
* [Meteocat](https://apidocs.meteocat.gencat.cat/)
* [TMB Developer Portal](https://developer.tmb.cat/)
