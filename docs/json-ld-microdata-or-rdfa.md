# JSON-LD, Microdata or RDFa?

Last [updated](/node/2946678/discuss) on

18 February 2019

There are three primary methods to output structured data on a website - JSON-LD, Microdata and RDFa. Which is best to use?  
This question is probably best answered through a combination of technical and practical assessments. The information below can help you assess whether JSON-LD, and by extension the Schema.org Metatag module is your best bet.

Also see [https://www.lullabot.com/articles/create-seo-juice-by-adding-json-ld-structured-data-to-drupal-8](https://www.lullabot.com/articles/create-seo-juice-by-adding-json-ld-structured-data-to-drupal-8)

[](#s-json-ld-as-a-standard-to-exchange-structured-data "Permalink to this headline")JSON-LD as a standard to exchange structured data
--------------------------------------------------------------------------------------------------------------------------------------

JSON-LD was ratified and made a W3C standard in 2014 - [https://www.w3.org/TR/json-ld/](https://www.w3.org/TR/json-ld/)  
It is the newest format to express structured data as defined by schema.org. It is also the only format that moves structured data out of the HTML body into head as a standalone data object, and hence keeps your markup clean and trim.

### [](#s-search-engine-support-status-as-of-july-2018 "Permalink to this headline")Search Engine support status (as of July 2018)

Google recommends JSON-LD over Microdata and RDFa - [https://developers.google.com/search/docs/guides/sd-policies](https://developers.google.com/search/docs/guides/sd-policies)  
Bing supports JSON-LD markup since [Fabrice Canel's announcement](https://searchengineland.com/bing-announces-bing-amp-viewer-json-ld-support-in-bing-webmaster-tools-300037) at SMX Advanced fair on the 12th June 2018. Bing has implemented this feature in the Bing Webmaster Tools interface and in the [Bing Markup Validator Tool](https://www.bing.com/toolbox/markup-validator).  
Yandex is fine with JSON-LD, they have a validator at [https://webmaster.yandex.com/tools/microtest/](https://webmaster.yandex.com/tools/microtest/)  
Baidu uncertain - [https://cloud.baidu.com/product/kg/schema](https://cloud.baidu.com/product/kg/schema) implies yes, search results imply no.