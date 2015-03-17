# LINZ LandOnline Cadastral Scripts (`linz_cadastral`) #

These scripts facilitate generating a number of Shapefiles from LINZ LandOnline data as provided to subscribers to the [LINZ LandOnline Bulk Data Extract](http://www.linz.govt.nz/survey-titles/landonline-data/landonline-bde/index.aspx) programme. They're also combined with the [Statistics NZ Digital Boundaries](http://www.stats.govt.nz/statistics-by-area/geography-mapping/download-digital-boundaries.htm).

Basically the scripts convert the eightyish tables in the LandOnline cadastral database into a few shapefiles based on usage themes:
  * Geocoding (address, road, suburb, city, district, region, postcode, etc)
  * Property parcels
  * Property titles
  * Roads

## Requirements ##
  * [Python](http://python.org) >= 2.4
  * [PostgreSQL](http://postgresql.org) 8+ & [PostGIS](http://postgis.refractions.net/)
  * [Proj4](http://trac.osgeo.org/proj/), preferably with the NZGD49 grid shift installed.
  * [GDAL](http://gdal.org/) (only needed if you want .prj files created for your exported SHPs)

In additon, the scripts have only been tested/run under Ubuntu Linux. They should work okay on any modern Linux distribution, and might work on Windows, but you will likely need to tweak paths/filename conventions/etc. (File bugs if you find problems!)

## Documentation ##

There are no releases for this set of scripts yet.

  1. Checkout the source:
```
svn checkout http://nz-geodata-scripts.googlecode.com/svn/trunk/linz_cadastral
```
  1. See the [README](http://nz-geodata-scripts.googlecode.com/svn/trunk/linz_cadastral/README) file in `linz_cadastral/README`
  1. Enjoy :)

## FAQ ##

(Feel free to add comments and ask further questions below)

#### Where do I get the source data from? ####

For the Stats NZ boundaries, you can [download them](http://www.stats.govt.nz/statistics-by-area/geography-mapping/download-digital-boundaries.htm). For the LandOnline data you'll need to subscribe to the [Data Extract http://www.linz.govt.nz/survey-titles/landonline-data/landonline-bde/index.aspx](Bulk.md) programme, or get hold of the data off someone who is already subscribed (the license terms are okay with that, LINZ has even released it for use by OpenStreetMap under a Creative Commons license). Hopefully we'll get the data hosted and online shortly for everybody.

#### Which set of Digital Boundaries do I download? ####

The scripts were written to use the boundaries when they were only available in NZ Map Grid (EPSG:27200), but we'll update that soon. The 2006 Level 2 boundaries contain a number of invalid geometries due to someone's dodgy simplification, so we'd recommend using the Level 1 boundaries until this is resolved.