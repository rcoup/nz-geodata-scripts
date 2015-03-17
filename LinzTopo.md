# LINZ NZTopo LSLIFF processing scripts (`linz_topo`) #

This script generates Shapefiles or PostGIS tables from the raw LSLIFF data (.iff files) as provided to purchasers of the LINZ NZTopo extracts. Each layer in the LSLIFF theme (a .iff file) ends up as a Shapefile or PostGIS table.

## Requirements ##
  * [Python](http://python.org) >= 2.4
  * [GDAL/OGR](http://gdal.org/), built with the Python bindings & the PostgreSQL driver. On Ubuntu or Debian Linux, the package you're after is "python-gdal"

In addition, the scripts have only been tested/run under Ubuntu Linux and Mac OSX. They should work okay on any modern Linux distribution, and might work on Windows, but you will likely need to tweak paths/filename conventions/etc. (File bugs if you find problems!)

## Documentation ##

There are no releases for these scripts yet.

  1. Checkout the source:
```
svn checkout http://nz-geodata-scripts.googlecode.com/svn/trunk/linz_topo
```
  1. See the [README](http://nz-geodata-scripts.googlecode.com/svn/trunk/linz_topo/README) file in `linz_topo/README`
  1. Enjoy :)

## FAQ ##

(Feel free to add comments and ask further questions below)

#### Where do I get the source data from? ####

  * From LINZ: http://www.linz.govt.nz/topography/topographic-data/vector-extracts/index.aspx

#### What are the SRIDs to use? ####

  * NZ Transverse Mercator (NZGD2000): [2193](http://spatialreference.org/ref/epsg/2193)
  * Chatham Islands Transverse Mercator (CITM2000): [3793](http://spatialreference.org/ref/epsg/3793) - you may need to add this to your GDAL coordinate definitions (pcs.csv) if you're using an older version of GDAL.
  * Some older Topo releases use Chathams Islands Map Grid - see the notes on the disc for details of this projection.