# Schema.org Coverage

Last [updated](/node/2942670/discuss) on

12 September 2020

Since the [Schema.org](https://schema.org/) list is huge, and growing, this module only provides a  
small subset of those values, but it is designed to be extensible. Several types  
are included which can be copied to add new types (groups) with any number of  
their own properties. The current list of Schema.org top-level (entity) object types includes:

*   [Schema.org/Article](https://schema.org/Article)
*   [Schema.org/Organization](https://schema.org/Organization)
*   [Schema.org/Person](https://schema.org/Person)
*   [Schema.org/VideoObject](https://schema.org/VideoObject)
*   [Schema.org/ImageObject](https://schema.org/ImageObject)
*   [Schema.org/Event](https://schema.org/Event)
*   [Schema.org/Movie](https://schema.org/Movie)
*   [Schema.org/TVSeries](https://schema.org/TVSeries)
*   [Schema.org/TVSeason](https://schema.org/TVSeason)
*   [Schema.org/TVEpisode](https://schema.org/TVEpisode)
*   [Schema.org/JobPosting](https://schema.org/JobPosting)
*   [Schema.org/Recipe](https://schema.org/Recipe)
*   [Schema.org/HowTo](https://schema.org/HowTo)
*   [Schema.org/QAPage](https://schema.org/QAPage)
*   [Schema.org/FAQPage](https://schema.org/FAQPage)
*   [Schema.org/Product](https://schema.org/Product)
*   [Schema.org/Service](https://schema.org/Service)
*   [Schema.org/Review](https://schema.org/Review)
*   [Schema.org/WebSite](https://schema.org/WebSite)
*   [Schema.org/WebPage](https://schema.org/WebPage)
*   [Schema.org/ItemList](https://schema.org/ItemList) (for Views)

Many second-level properties are available to use on the above, including:

*   [Schema.org/Action](https://schema.org/Action)
*   [Schema.org/Address](https://schema.org/Address)
*   [Schema.org/Brand](https://schema.org/Brand)
*   [Schema.org/BreadcrumbList](https://schema.org/BreadcrumbList)
*   [Schema.org/Country](https://schema.org/Country)
*   [Schema.org/MonetaryAmount](https://schema.org/MonetaryAmount)
*   [Schema.org/NutritionInformation](https://schema.org/NutritionInformation)
*   [Schema.org/Offer](https://schema.org/Offer)
*   [Schema.org/OpeningHoursSpecification](https://schema.org/OpeningHoursSpecification)
*   [Schema.org/Organization](https://schema.org/Organization)
*   [Schema.org/Person](https://schema.org/Person)
*   [Schema.org/Place](https://schema.org/Place)
*   [Schema.org/ProgramMembership](https://schema.org/ProgramMembership)
*   [Schema.org/Question](https://schema.org/Question)
*   [Schema.org/Answer](https://schema.org/Answer)
*   [Schema.org/HowToStep](https://schema.org/HowToStep)
*   [Schema.org/Rating](https://schema.org/Rating)
*   [Schema.org/Review](https://schema.org/Rating)

It's fairly easy to add more properties to these types. To add properties that most users would want, like things that Google requires, provide a patch. To add properties that are specific to your own use case, you can create a custom module with any properties you want to add. The Article Example module shows how to do it.

To add more schema types, see the [development instructions (8.1)](https://www.drupal.org/docs/8/modules/schemaorg-metatag/developer-instructions) or [development instructions (8.2)](https://www.drupal.org/docs/contributed-modules/schemaorg-metatag/developer-instructions-for-82-branch). It is neither hard nor tedious, so don't be afraid to give it a shot. If you want to add something you think others would want to use, once you have a working submodule please create an issue in the [module's issue queue](https://www.drupal.org/project/issues/schema_metatag?categories=All) and post a patch for review.