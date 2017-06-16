# Atlas Brasil

This demo is simple.

It shows how to fetch links from `http://www.atlasbrasil.org.br/2013/pt/download/` and using a configuration file, decide what title to download. All the downloaded `xlsx` files will then have each of their defined inner sheets parsed to CSV **without having to know the fields name/quantity in advance**

This is a sample `config.json` file - yes, that's all required configuration:

```json
[{
    "title": "Atlas dos Municípios",
    "sheets": [ "MUN 91-00-10", "BR 91-00-10", "UF 91-00-10" ]
}]
```

All the links from the webpage have an associated title. For each title, the engine will download the workbook and parse to csv all of the sheets defined into `sheets: []`.

The above example will output to `landing/` the following files:

```
atlas2013_dadosbrutos_pt.xlsx
atlas2013_dadosbrutos_pt.UF 91-00-10.csv
atlas2013_dadosbrutos_pt.MUN 91-00-10.csv
atlas2013_dadosbrutos_pt.BR 91-00-10.csv
```

# Multiple files

The `config.json` file can have as many sources as we want, as long as the file is a XLSX and the listed sheets start at `0, 0` index - even though these limitations could be generalized within the process.

```json
[{
  "title": "Source 01",
  "sheets": []
},{
  "title": "Source 02",
  "sheets": []
}]

For other extensions, we could check the file extension and implement a parser.

For different start indexes, we could externalize this to the config file.