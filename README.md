# Pentaho web crawling samples

This project holds a couple of samples of how to do web crawling using Pentaho data integration.

### Dependencies

You should place the [Jodd](http://jodd.org/download/) library into your `data-integration/lib` folder.

# Samples

There are two examples implemented

* `kettle/dados.gov.br` - gets one specific dataset html page and retrieves all csv URLs - that can be passed to result and downloaded at job level
* `kettle/ipeadata` - gets information from ipeadata.gov.br that enables accessing their API to download data in CSV, XLSX and other formats;
