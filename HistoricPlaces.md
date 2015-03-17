# NZ Historic Places Register (`historic_places`) #

Scrapes the NZ Historic Places register from http://www.historic.org.nz/register.html and produces a JSON data file

Outputs a JSON array with an object for each entry, containing
each of the defined fields for that entry. Strips <br /> tags and
redundant whitespace. Will skip any errors it finds, outputting
a message to stderr.

See [example.json](http://nz-geodata-scripts.googlecode.com/svn/trunk/historic_places/example.json) for an idea of what the output will look like (example entries are [#22](http://www.historic.org.nz/Register/ListingDetail.asp?RID=22) and [#7](http://www.historic.org.nz/Register/ListingDetail.asp?RID=7)).

**Please be considerate of their site.**

## Requirements ##
  * [Python](http://python.org) >= 2.4
  * [BeautifulSoup](http://www.crummy.com/software/BeautifulSoup/) for HTML parsing
  * [Simplejson](http://code.google.com/p/simplejson/) for JSON output
  * [Workerpool](http://code.google.com/p/workerpool/) (optional) allows us to do multithreaded grabbing.

In addition, the script has only been tested/run under Ubuntu Linux & Mac OSX. It should work on Windows (File bugs if you find problems!).

## Documentation ##

There are no releases for this script yet.

  * Checkout the source:
```
svn checkout http://nz-geodata-scripts.googlecode.com/svn/trunk/historic_places
```

By default, running this script will download all the entries and print
the JSON to stdout. Add a set of records IDs (eg. [#22](http://www.historic.org.nz/Register/ListingDetail.asp?RID=22)) to the command line
to only output the specified records. "`-v`" as the first argument will
print out the HTML page and HTTP headers for each entry retrieved.

  * Get _ALL_ entries (~5500 entries from ~9500 URLs):
```
./historic-places-scraper.py > historic.json
```

  * Just grab entries [#22](http://www.historic.org.nz/Register/ListingDetail.asp?RID=22) and [#7](http://www.historic.org.nz/Register/ListingDetail.asp?RID=7):
```
./historic-places-scraper.py 22 7 > historic.json
```

  * Debug entry [#22](http://www.historic.org.nz/Register/ListingDetail.asp?RID=22), printing the HTML and headers:
```
./historic-places-scraper.py -v 22
```

## FAQ ##

1. Why are there so many 500 errors reported?
> Their database is missing plenty of ID numbers in the sequence, and missing numbers seem to return 500 (Server Error) responses instead of 404 (Not Found) responses.

2. Why aren't the fields the same across entries?
> Entries seem to have vastly different details - we grab whatever is there. See the top of the script file for a list of keys we use in the output.

(Feel free to add comments and ask further questions below)