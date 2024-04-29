Performance Considerations
==========================

Last [updated](/node/3024933/discuss) on

10 January 2019

Follow these simple steps and your site performance when using schema\_metatag module should be fine:

1.  Enable only the schema\_metatag submodules you need. The modules you enable would normally map to the top-level content types on your site.
2.  Take advantage of the metatag settings at admin/config/search/metatag/settings. There open up each content type and check only the groups you want to use on that content type. So select 'Schema.org Article' only on the Article content type, 'Schema.org Event' only on the Event content type, etc.
3.  For the most part you should only need a couple Schema.org groups on any given content type.
4.  Try to be as specific as possible when you mark things up, and generally only mark up the primary content on the page. This is not only a performance strategy, but also good SEO.

If used wrongly, the schema\_metatag module can make editing pages on your site a painfully slow experience. The problem is that the metatag module creates a gigantic form element with all possible values and displays that on each metatag field.

That said, [the demo site](https://master-u76mzgdzaglzpot6twbjukcxsbluwebm.tugboat.qa/) has every module enabled and is still easy to use because it takes advantage of the metatag settings. (admin/config/search/metatag/settings).