Pivot
=====

Last [updated](/node/2945949/discuss) on

26 October 2020

A new option is an option to "Pivot" multiple values for the Person, Organization, Address, Offer and some other objects that might hold multiple values. If selected, this will change the result from:

    <script type="application/ld+json">{
        "@context": "http://schema.org",
        "@graph": [
            {
                "@type": "Event",
                "name": "Premier",
                "url": "example.com/event/premier",
                "description": "Lorem ipsum dolor sit amet, consectetur.",
                "offers": [
                    {
                        "@type": "Offer",
                        "price": [
                          "10",
                          "20",
                        ],
                        "priceCurrency": "USD",
                        "url": "http://amazon.com"
                    },
                ],
                "actor": {
                    "@type": "Person",
                    "name": [
                        "Micky Mouse",
                        "Donald Duck",
                        "Tweety Bird"
                    ],
                    "url": [
                        "http://example.com/person/mickey-mouse",
                        "http://example.com/person/donald-duck",
                        "http://example.com/person/tweety-bird"
                    ],
                }
            },
        ]
    }</script>

to:

    <script type="application/ld+json">{
        "@context": "http://schema.org",
        "@graph": [
            {
                "@type": "Event",
                "name": "Premier",
                "url": "example.com/event/premier",
                "description": "Lorem ipsum dolor sit amet, consectetur.",
                "offers": [
                    {
                        "@type": "Offer",
                        "price": "10",
                        "priceCurrency": "USD",
                        "url": "http://amazon.com"
                    },
                    {
                        "@type": "Offer",
                        "price": "20",
                        "priceCurrency": "USD",
                        "url": "http://amazon.com"
                    }
                ],
                "actor": {
                    {
                        "@type": "Person",
                        "name": "Mickey Mouse",
                        "url": "http://example.com/person/mickey-mouse",
                    },
                    {
                        "@type": "Person",
                        "name": "Daffy Duck",
                        "url": "http://example.com/person/daffy-duck",
                    },
                    {
                        "@type": "Person",
                        "name": "Tweety Bird",
                        "url": "http://example.com/person/tweety-bird",
                    },
                }
            },
        ]
    }</script>