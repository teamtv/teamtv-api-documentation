# vMix integration

TeamTV API makes it possible to include stats data from TeamTV into your vMix.

## vMix Data Sources

vMix is able to load data via a [Data Source](https://www.vmix.com/help24/index.htm?DataSources.html). There are many YouTube videos available about how to use the Data Sources. On from vMix itself can be found [here](https://www.youtube.com/watch?v=t9CcKd9GeSY). 


## How to integrate 

To use vMix Data Sources together with TeamTV API you have to create a json Data Source.
<img src="/images/vmix-datasource-create.png" />

Within this screen enter in the `URL/Filename` field the url of the TeamTV Reporting API.
```bash
https://reporting-api.teamtvsport.com/report/<reportName>/<sportingEventId>?Authorization=<Authorization>&X-Resource-Group-Id=<resourceGroupId>
```

When you hit 'OK' the data will be fetched and the output should look like:
<img src="/images/vmix-datasource-data.png" />

*Make sure you set the `Update data every` field at the bottom to at least `10000` Milliseconds.*

When you include the data in a graphic it can look like this:

<img src="/images/vmix-datasource-output.png" />
*Image provided by [Ferdi Bouwman](https://www.linkedin.com/in/ferdibouwman/) from korfball club [AVO](https://avoassen.nl/)*


## Available reports

As of 2022-04-15 the following reports are available:

### Korfball

The korfball report can be fetched by providing `korfball_vmix` as `reportName`. 
