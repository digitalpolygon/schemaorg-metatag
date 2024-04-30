# Example Article setup

Last [updated](/node/3142421/discuss) on

26 May 2020

The following assumes there is an entity reference field to a **Tags** vocabulary (used in the about section) and another field called **field\_media\_image** that references a **Media** entity that points to an **image** that can be displayed with the **large** image style. Also assuming this is an article behind a paywall, to illustrate how that would be configured.

    @type: NewsArticle
    headline: [node:title]
    name: [node:title]
    about: [node:field_tags]
    description: [node:summary]
    
    IMAGE
    @type: ImageObject
    representative Of Page: TRUE
    url: [node:field_media_image:entity:field_media_image:large:url]
    width: [node:field_media_image:entity:field_media_image:large:width]
    height: [node:field_media_image:entity:field_media_image:large:height]
    
    datePublished: [node:created:html_datetime]
    dateModified: [node:changed:html_datetime]
    
    HASPART
    @type: WebPageElement
    isAccessibleForFree: False
    cssSelector: .paywall1,.paywall2
    isAccessibleForFree: FALSE
    
    AUTHOR
    @type: Person
    Pivot: FALSE
    name: [node:author:display_name]
    url: [node:author:url]
    
    PUBLISHER
    @type: Organization
    name: [site:name]
    url: [site:url]
    LOGO
    @type: ImageObject
    Pivot: FALSE
    representative Of Page: FALSE
    url: sites/defaultfiles/logo.png
    width: 100
    height: 93
    
    mainEntityOfPage: [current-page:url]