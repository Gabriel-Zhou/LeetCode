Komadu JavaScript messaging client
=========

A lightweight javascript messaging client for Komadu Provenance Toolset. This client supports sending provenance notifications and querying provenance graph. It provides command line usage and easy-to-use npm module usage which can be integrated into web UIs or other infrastructure. Please refer to github Komadu repository https://github.com/Data-to-Insight-Center/komadu or find this module on http://npmjs.org website with module name "client-core-messaging-js".

## Installation

    npm install client-core-messaging-js --save

## Usage -- command line usage

Command line usage requires node module "amqplib" to run.

    npm install amqplib --save

    //Sending provenance notifications
    node ./bin/sendNotification.js <komadu.json> <notification xml>
    
    //Querying provenance graph
    node ./bin/query.js <komadu.json> <query xml> <output path>

  One example configuration json file for Komadu messaging client is as below:

    {
     "messaging":
     {
        "username":"guest",
        "password":"guest",
        "hostname":"localhost",
        "hostport":"5672",
        "virtualhost":"/",
        "exchangename":"KomaduExchange",
        "queuename":"KomaduQueue",
        "routingkey":"KomaduKey"
     },
     "schema":
     {
        "ingest":"$CLIENT_HOME/config/komadu_ingest_schema.xsd",
        "query":"$CLIENT_HOME/config/komadu_query_schema.xsd"
     }
    }


## Usage -- node module usage

  var scapegoat = require('scapegoat')
      escape = scapegoat.escape,
      unescape = scapegoat.unescape;

  var html = '<h1>Hello World</h1>',
      escaped = escape(html),
      unescaped = unescape(escaped);

  console.log('html', html, 'escaped', escaped, 'unescaped', unescaped);

## Tests
    
    npm test

## Contributing

In lieu of a formal styleguide, take care to maintain the existing coding style.
Add unit tests for any new or changed functionality. Lint and test your code.

## Release History

* 0.1.0 Initial release
