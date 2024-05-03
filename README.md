# Schema.org Metatag

This project extends Drupal's Metatag module to display structured data as JSON-LD in the head of web pages. Either hard-code properties or identify patterns using token replacements. Using the override system in Metatag module you can define default structured data values for all content types, override the global content defaults for a particular content type, or even override everything else on an individual node to provide specific values for that node.

Read more about Schema.org, JSON-LD, and how this module works in an article on Lullabot.com: [Create SEO Juice From JSON LD Structured Data in Drupal](https://www.lullabot.com/articles/create-seo-juice-by-adding-json-ld-structured-data-to-drupal-8).

Since the [Schema.org](https://schema.org/) list is huge, and growing, this module only provides a small subset of those values, but it is designed to be extensible. Several types are included which can be copied to add new types (groups) with any number of their own properties.

The module creates the following Schema.org object types:

- [Article](https://schema.org/Article)
- [Book](https://schema.org/Book)
- [Course](https://schema.org/Course)
- [Event](https://schema.org/Event)
- [FAQPage](https://schema.org/FAQPage)
- [HowTo](https://schema.org/HowTo)
- [ImageObject](https://schema.org/ImageObject)
- [ItemList](https://schema.org/ItemList) (for Views)
- [JobPosting](https://schema.org/JobPosting)
- [Movie](https://schema.org/Movie)
- [Organization](https://schema.org/Organization)
- [Person](https://schema.org/Person)
- [Place](https://schema.org/Place)
- [Product](https://schema.org/Product)
- [QAPage](https://schema.org/QAPage)
- [Recipe](https://schema.org/Recipe)
- [Review](https://schema.org/Review)
- [Service](https://schema.org/Service)
- [SpecialAnnouncement](https://schema.org/SpecialAnnouncement)
- [TVEpisode](https://schema.org/TVEpisode)
- [TVSeason](https://schema.org/TVSeason)
- [TVSeries](https://schema.org/TVSeries)
- [VideoObject](https://schema.org/VideoObject)
- [WebPage](https://schema.org/WebPage)
- [WebSite](https://schema.org/WebSite)

Many second-level properties are available to use on the above, including:

- [Action](https://schema.org/Action)
- [Address](https://schema.org/Address)
- [Answer](https://schema.org/Answer)
- [Brand](https://schema.org/Brand)
- [BreadcrumbList](https://schema.org/BreadcrumbList)
- [Country](https://schema.org/Country)
- [HowToStep](https://schema.org/HowToStep)
- [MonetaryAmount](https://schema.org/MonetaryAmount)
- [NutritionInformation](https://schema.org/NutritionInformation)
- [Offer](https://schema.org/Offer)
- [OpeningHoursSpecification](https://schema.org/OpeningHoursSpecification)
- [Organization](https://schema.org/Organization)
- [Person](https://schema.org/Person)
- [Place](https://schema.org/Place)
- [ProgramMembership](https://schema.org/ProgramMembership)
- [Question](https://schema.org/Question)
- [Rating](https://schema.org/Rating)
- [Review](https://schema.org/Review)

Using the override system in Metatag module you can define default structured data values for all content types, override the global content defaults for a particular content type, or even override everything else on an individual node to provide specific values for that node. Hard-code properties or identify patterns using token replacements.

## Validation

- [Schema Markup Validator](https://validator.schema.org/)
- [Rich Results Test](https://search.google.com/test/rich-results)

### Additional Resources

- [Getting started with schema.org using Microdata](https://schema.org/docs/gs.html)
- [Schema.org Full Hierarchy](https://schema.org/docs/full.html)
- [Understand how structured data works](https://developers.google.com/search/docs/advanced/structured-data/intro-structured-data)

If you are new to structured data you should definitely read the first reference carefully.

For more information about the Metatag module and how to set it up, see [Drupal Metatag Module Documentation](https://www.drupal.org/docs/8/modules/metatag).

## Known Issues

- To populate the image width and height properties, use the appropriate tokens. The core Token module provides image height and width token, for example, the token `[node:field_image:0:width]` will be replaced with the width of the first image in field_image on the current node.

## Development Instructions

This module defines Metatag groups that map to Schema.org types, and metatag tags for Schema.org properties, then steps in before the values are rendered as metatags, pulls the Schema.org values out of the header created by Metatag, and instead renders them as JSON-LD when the page is displayed.

The module includes a base group class and several base tag classes that can be extended. Many properties are simple key/value pairs that require nothing more than extending the base class and giving them their own ids. Some are more complex, like Person and Organization, and BreadcrumbList, and they collect multiple values and serialize the results.

The development process for adding groups and properties:

- Create groups at `MODULE_NAME/src/Plugins/metatag/Group` and properties at `MODULE_NAME/src/Plugins/metatag/Tag`. Each tag extends the appropriate base class.

In either case, you should be able to copy one of the existing modules as a starting point.

There is an included module, Schema.org Article Example, that shows how other modules can add more properties to types that are already defined.

## Examples and Hints

Using this module, the code in the head might end up looking like this:
```
<script type="application/ld+json">{
    "@context": "https://schema.org",
    "@graph": [
        {
            "@type": "Article",
            "description": "Curabitur arcu erat, accumsan id imperdiet et.",
            "datePublished": "2009-11-30T13:04:01-0600",
            "dateModified": "2017-05-17T19:02:01-0500",
            "headline": "Curabitur arcu erat]",
            "author": {
                "@type": "Person",
                "name": "Minney Mouse",
                "sameAs": "https://example.com/user/2"
            },
            "publisher": {
                "@type": "Organization",
                "name": "Example.com",
                "sameAs": "https://example.com/",
                "logo": {
                    "@type": "ImageObject",
                    "url": "https://example.com/sites/default/files/logo.png",
                    "width": "600",
                    "height": "60"
                }
            },
            "mainEntityOfPage": {
                "@type": "WebPage",
                "@id": "https://example.com/story/example-story"
            },
        },
    ]
}</script>
```

## Contributing

The `composer.json` file should be kept normalized using `ergebnis/composer-normalize`:

- `composer require --dev ergebnis/composer-normalize`
- `composer normalize modules/contrib/schema_metatag/composer.json`

## Credits

The initial development was by Karen Stevenson](https://www.drupal.org/u/karens).
