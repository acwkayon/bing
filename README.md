# Bing Map 

This [MLHub](https://mlhub.ai) package provides a demonstration and
command line tools built from Bing Map REST service provided through
Microsoft. This service can generate a list of coordinates (latitude
and longitude) based on the provided location. 

A Bing Map Key is required, allowing up to 50K geocodes a day, or 
150K total. Through
the [Bing Map Account](https://www.bingmapsportal.com/) create a Bing 
Map accont and use the key from the account for the *demo*. 


**Warning** Unlike the MLHub models in general these Bimg Map REST services
use *closed source services* which have no guarantee of ongoing
availability and do not come with the freedom to modify and share.

The Bing Map source code is available from
<https://github.com/JingjingShii/bing>.

## Quick Start

```console

$ ml geocode bing back creek
$ ml geocode bing back creek --maxres 3
$ ml geocode bing back creek --inclnb 1
$ ml geocode bing back reek --verbose True
$ ml geocode bing back reek --google True
$ ml geocode bing back reek --to out.csv
```

## Usage

- To install mlhub (Ubuntu):

		$ pip3 install mlhub
		$ ml configure

- To install, configure, and run the demo:

		$ ml install   bing
		$ ml configure bing
		$ ml readme    bing
		$ ml commands  bing
		$ ml demo      bing
		
- Command line tools:

		$ ml geocode bing [(location) <location or csv file>] [(--inclnb) <Include the neighborhood>] [(--maxres) <Maximun number of locations to return>] [(--google) <Show the location in the Google Map>] [(--to) <Output as the csv file>] [(--verbose) <Print out the results>]
    
## Command Line Tools

In addition to the *demo* command below, the package provides a number
of useful command line tools.

### *geocode*

The *geocode* command will generate a list of coordinate pairs for the provided
location or csv file. Each coordinate pair includes latitude and longitude. If the provided
location is specific, the result will be a list with one element. If the location
is ambiguous, such as a duplicate name in Australia, a list with several elements 
will be shown. It has the option to specify the maximum number of coordinates to 
return in the response. The number is between 1-20, and the default is 5. Also,
this service provides the option to include the neighborhood with the address
information when it is available. The default is 0 (Do not include neighborhood
information). We provide --google option to show the location in the Google Map 
via link. We also provide --verbose to print out the result and --to to store the 
output in csv file. 

**Note**: For the input CSV file, we only accept the CSV files that don't have a title and
each location in a single row. As for the output CSV, each location's result will be in one
row. 

```console
$ ml geocode bing PriceLine Pharmacy Albany Creek
$ ml geocode bing back reek --maxres 3
$ ml geocode bing back reek --inclnb 1
$ ml geocode bing back reek --verbose True
$ ml geocode bing back reek --google True
$ ml geocode bing back reek --to out.csv

$ brave-browser `ml geocode bing --max=1 --osm albany creek`

$ brave-browser `ml geocode bing bunnings mentone 23-27 nepean hwy mentone vic 3194 --osm`
```

## Demonstration
```console
========
Bing Map
========

Welcome to Bing Maps REST service. This service can find the the
latitude and longitude coordinates that correspond to location
information provided  as a query string.

Press Enter to continue: 

=======
GEOCODE
=======

 This part is to generate the latitude and longitude coordinates based
on the query. The result might be several. Here we set the query to
Priceline Pharmacy Albany Creek. In this case, it will generate a pair
of coordinates.

Press Enter to continue: 


Latitude: -27.35361099243164 Longitude: 152.96832275390625

```
