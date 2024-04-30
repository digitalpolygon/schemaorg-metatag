# Developer Instructions for 8.1 Branch

Last [updated](/node/2955771/discuss) on

12 September 2020

[](#s-extending-an-existing-schema "Permalink to this headline")Extending an existing schema
--------------------------------------------------------------------------------------------

Schema.org Metatag module contains an example module, schema\_article\_example, that shows how the Article schema can be extended without altering the schema\_article module itself. Using this as a template basically only entails file name changes, and naming edits in the code. This is a great option if the extension is for an arcane property, or proprietary to you.  It is also useful since future module updates won't overwrite your code.

Alternatively, you can extend one of the existing submodules. We recommend you check out the current development branch via git for this. Then post [your patch](https://www.drupal.org/node/707484) to the [issue queue](https://www.drupal.org/project/issues/schema_metatag) for inclusion into the module. This is your best option if the extension is of broad value to most folks, such as adding a property required or recommended by search engines.

[](#s-adding-support-for-a-new-schema "Permalink to this headline")Adding support for a new schema
--------------------------------------------------------------------------------------------------

For a completely new schema, let's use the Service schema as an example. A review of [schema.org/Service](https://schema.org/Service) shows that Service has many of the same properties as Product. So as a decent first cut we will clone the schema\_product module. Use an analogous approach for any other schemas.

1.  Copy the schema\_product directory and name it schema\_service. Rename each file in schema\_service to contain _service_ in its name instead of _product_.
2.  Go through all code files and change _product_ to _service_. You will find lowercase and uppercase instances, change them all and retain case.
3.  You may want to edit description text for certain types. Generally these should match what you find at schema.org, but you can often do better by being more precise.
4.  Clear Drupal cache, and enable your new module. If none is found you haven't completed your renaming.
5.  Go to /admin/config/metatag and check whether your new schema shows up, and then check whether all fields show up correctly and are free of typos.
6.  The only tricky part of this process is finding the right base class to use for each property. A simple text or numeric value would use the default class, SchemaNameBase. More complicated properties will extend other classes. A partial list is below.
7.  Test your submodule on a node or sitewide by filling in values or tokens, and check the output on a relevant node.
8.  Run the JSON-LD code through Google's validator at [https://search.google.com/test/rich-results](https://search.google.com/test/rich-results).
9.  [Create a patch](https://www.drupal.org/node/707484) from your code and post it into a new issue in [Schema.org Metatag's issue queue](https://www.drupal.org/project/issues/schema_metatag).

[](#s-available-base-classes "Permalink to this headline")Available base classes
--------------------------------------------------------------------------------

The list of available base classes changes frequently, but a partial list is below. Look in the "/src/Plugin/metatag/Tag" directory of your repository to see the complete list. For example, on [http://schema.org/Article](http://schema.org/Article) there is an 'author' property that should be either a [http://schema.org/Person](http://schema.org/Person) object or a [http://schema.org/Organization](http://schema.org/Organization) object. You would set up the 'author' tag to extend the 'SchemaPersonOrg' class.

### [](#s-default-objects "Permalink to this headline")Default objects

*   SchemaNameBase - the default class, suitable for simple text or numeric values.
*   SchemaTypeBase - for the '@type' property used on all objects.

### [](#s-thing-objects "Permalink to this headline")Thing objects

*   SchemaPersonOrgBase - for a property that is either a Person or Organization.
*   SchemaEventBase - for a property that is an Event.
*   SchemaImageBase - for a property that is an Image.
*   SchemaCreativeWorkBase - for a property that is any type of CreativeWork.
*   SchemaThingBase - for a property that is any type of Thing.

### [](#s-location-objects "Permalink to this headline")Location objects

*   SchemaAddressBase - for a property that is an Address object.
*   SchemaGeoBase - for a property that is geographic coordinates.
*   SchemaPlaceBase - a Place object, a complex object that includes the name of a place along with an embedded Address object and A Geo object.
*   SchemaCountryBase - a property that is a Country object.

### [](#s-miscellaneous-objects "Permalink to this headline")Miscellaneous objects

*   SchemaActionBase - for a property that is an Action object.
*   SchemaDateBase - for a property that is a Date or Datetime object.
*   SchemaDurationBase - for a property that is a Duration object.
*   SchemaOfferBase - for a property that is an Offer object.
*   SchemaProgramMembershipBase - for a property that is a ProgramMembership object.