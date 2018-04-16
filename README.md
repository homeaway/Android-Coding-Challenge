## HomeAway Android Coding Challenge

HomeAway takes great care in how we select members of our engineering team. This technical challenge will help us get an idea of how you would use software to solve problems for our end users.

We know that your time is important, so we’ve designed the challenge with that in mind. An acceptable solution might take between 2-8 hours depending on how familiar you are with Android development. Nevertheless, please feel free to spend as much time as you’d like crafting your preferred solution. We hope you have fun building it!

### Mission: Seattle Place Search!

Your mission is to create a three-screen application that allows users to: search for places in Seattle, Washington using the [Foursquare API](https://developer.foursquare.com/places-api); view their search results in a list or on a map; and view the individual details of each search result.

The first screen should display an input field that allows users to search for places (for example, “coffee”, “pizza”, “Whole Foods”, etc) and, upon executing a search, should display the results in a list. Clicking an item in the list should launch a details screen. The details screen should show the place’s location on a map (for example, using [Google Maps](https://developers.google.com/maps/documentation/static-maps/)), provide details about the place, including website, and the user should be able to favorite the place on this screen.

On the main screen, when search results are visible, the screen should include a Floating Action Button. This button, when clicked, should a full-screen map with a pin marking the location of each search result. Clicking a pin should show the name of the place on the map, and clicking on the name should then open the details screen for the given place.

### Requirements

1. The main screen should display a search input, and should use industry best practices to perform a typeahead search against the Foursquare API.
2. When a search returns results, these should be displayed in a list format. Each list item should provide, at a minimum, the name of the place (e.g., Flitch Coffee), the category of the place (e.g., Coffee Shop), the icon from the response, the distance from the center of Seattle (47.6062° N, 122.3321° W) to the place, and whether the place has been favorited by the user. Clicking a list item should launch the details screen for that place.
3. When a search returns results, the main screen should include a [Floating Action Button](https://developer.android.com/reference/android/support/design/widget/FloatingActionButton.html). Clicking the Floating Action Button should launch a full-screen map with a pin for every search result. Clicking a pin should show the name of the place on the map, and clicking on the name should then open the details screen for the given place.
4. The details screen for a place should use a collapsible toolbar layout to show a map in the upper half of the screen, with two pins -- one, the location of search result, and the other, the center of Seattle. The bottom half of the details screen should provide details about the place, including whether or not the place is favorited, and should include a link to the place’s website (if it exists). Clicking this link should open an external Intent to a browser installed on the device.
5. Favorite selections should be changeable, should persist across launches of the app, and should show correctly on both the main and details screens.
6. The user should be able to navigate between screens according to Android platform conventions.
7. Include instructions for building the application and any relevant documentation in a README.md file
8. Please post your submission on github, or tar and zip the project directory for email or hosting on a file sharing service.

Feel free to use any libraries you feel are appropriate solutions to your technical needs.

### Notes

You will need to sign up for a free [Foursquare](https://developer.foursquare.com/places-api) account and get an API key to use it. Foursquare has a generous free tier, and the documentation describes integration as well as sample usage. A query to the Foursquare Places API could look something like:

```
curl -X GET -G 'https://api.foursquare.com/v2/venues/search' \
    -d client_id="CLIENT_ID"  \
    -d client_secret="CLIENT_SECRET" \
    -d near="Seattle,+WA" \
    -d query="coffee" \
    -d v="20180401" \
    -d limit=20
```

To display a map, you may use any solution you prefer. We suggest, for convenience, the [Google Static Map API](https://developers.google.com/maps/documentation/static-maps/) for the details screen and the [Google Maps Android API](https://developers.google.com/maps/android/) for the fullscreen map. Both have acceptable free tier limits and are well-documented.

For quick and easy icons, consider using the [Material icons](https://material.io/icons/).

### Considerations

We’re upping our game here at HomeAway, and we aim to create world-class app experiences for our customers. Among other criteria, your submission will be evaluated on:

1. Implementation of the stated requirements
2. Application Architecture
3. The general quality of the code and it’s resistance to crashing
4. Your use of Android coding conventions
5. Knowledge and usage of Android libraries and sdk’s
6. Clarity of communications in comments and other documentation
7. UI and UX -- while we don’t want you to spend any time creating custom icons or other assets, the app should look clean and generally obey the Human Interface Guidelines

Oh, and don’t worry if your app has personality or a sense of humor. We want you to have fun!

Good Luck,

Your Friends at HomeAway

### Sample Foursquare Response

For your convenience, below is a sample JSON response from the Foursquare Places Search API.

```
{
   "meta":{
      "code":200,
      "requestId":"5ad514b7db04f515c2b59594"
   },
   "response":{
      "venues":[
         {
            "id":"52d456c811d24128cdd7bc8b",
            "name":"Storyville Coffee Company",
            "contact":{
               "phone":"2067805777",
               "formattedPhone":"(206) 780-5777",
               "twitter":"storyville"
            },
            "location":{
               "address":"1001 1st Ave",
               "crossStreet":"at Madison St",
               "lat":47.60475923205166,
               "lng":-122.33636210125788,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.60475923205166,
                     "lng":-122.33636210125788
                  }
               ],
               "postalCode":"98104",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "1001 1st Ave (at Madison St)",
                  "Seattle, WA 98104",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":true,
            "stats":{
               "tipCount":43,
               "usersCount":1432,
               "checkinsCount":2443
            },
            "url":"https:\/\/www.facebook.com\/StoryvilleCoffee",
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "storeId":"",
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[
               {
                  "id":"556e5ca0bd6a82902e297f0f"
               }
            ],
            "hasPerk":false
         },
         {
            "id":"57e95a82498e0a3995a43e90",
            "name":"Anchorhead Coffee Co",
            "contact":{

            },
            "location":{
               "address":"1600 7th Ave Ste 105",
               "crossStreet":"Olive Way",
               "lat":47.61340942776967,
               "lng":-122.33469499761385,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.61340942776967,
                     "lng":-122.33469499761385
                  }
               ],
               "postalCode":"98101",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "1600 7th Ave Ste 105 (Olive Way)",
                  "Seattle, WA 98101",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":false,
            "stats":{
               "tipCount":30,
               "usersCount":779,
               "checkinsCount":2132
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":2,
               "summary":"2 people are here",
               "groups":[
                  {
                     "type":"others",
                     "name":"Other people here",
                     "count":2,
                     "items":[

                     ]
                  }
               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"49d3e558f964a520225c1fe3",
            "name":"Cherry Street Coffee House",
            "contact":{
               "phone":"2066219372",
               "formattedPhone":"(206) 621-9372",
               "twitter":"cherrystreet"
            },
            "location":{
               "address":"103 Cherry St",
               "crossStreet":"at 1st Ave",
               "lat":47.6027673689831,
               "lng":-122.33415096584942,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.6027673689831,
                     "lng":-122.33415096584942
                  }
               ],
               "postalCode":"98104",
               "cc":"US",
               "neighborhood":"Seattle Central Business District",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "103 Cherry St (at 1st Ave)",
                  "Seattle, WA 98104",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":true,
            "stats":{
               "tipCount":38,
               "usersCount":1953,
               "checkinsCount":5412
            },
            "url":"http:\/\/cherryst.com",
            "hasMenu":true,
            "menu":{
               "type":"Menu",
               "label":"Menu",
               "anchor":"View Menu",
               "url":"https:\/\/foursquare.com\/v\/cherry-street-coffee-house\/49d3e558f964a520225c1fe3\/menu",
               "mobileUrl":"https:\/\/foursquare.com\/v\/49d3e558f964a520225c1fe3\/device_menu"
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"52251f9511d2b2f238901956",
            "name":"Storyville Coffee Company",
            "contact":{
               "phone":"2067805777",
               "formattedPhone":"(206) 780-5777",
               "twitter":"storyville"
            },
            "location":{
               "address":"94 Pike St #34",
               "crossStreet":"1st Ave (Pike Place Market)",
               "lat":47.608968412285684,
               "lng":-122.34069716145795,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.608968412285684,
                     "lng":-122.34069716145795
                  }
               ],
               "postalCode":"98101",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "94 Pike St #34 (1st Ave (Pike Place Market))",
                  "Seattle, WA 98101",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":true,
            "stats":{
               "tipCount":121,
               "usersCount":3512,
               "checkinsCount":5789
            },
            "url":"https:\/\/www.facebook.com\/StoryvilleCoffee",
            "hasMenu":true,
            "menu":{
               "type":"Menu",
               "label":"Menu",
               "anchor":"View Menu",
               "url":"https:\/\/foursquare.com\/v\/storyville-coffee-company\/52251f9511d2b2f238901956\/menu",
               "mobileUrl":"https:\/\/foursquare.com\/v\/52251f9511d2b2f238901956\/device_menu"
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "storeId":"",
            "hereNow":{
               "count":2,
               "summary":"2 people are here",
               "groups":[
                  {
                     "type":"others",
                     "name":"Other people here",
                     "count":2,
                     "items":[

                     ]
                  }
               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[
               {
                  "id":"556e5ca0bd6a82902e297f0f"
               }
            ],
            "hasPerk":false
         },
         {
            "id":"545803de498e7e758ac5605e",
            "name":"Elm Coffee Roasters",
            "contact":{

            },
            "location":{
               "address":"240 2nd Avenue Ext S Ste 103",
               "lat":47.600152370806754,
               "lng":-122.33094380272051,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.600152370806754,
                     "lng":-122.33094380272051
                  }
               ],
               "postalCode":"98104",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "240 2nd Avenue Ext S Ste 103",
                  "Seattle, WA 98104",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":true,
            "stats":{
               "tipCount":68,
               "usersCount":1484,
               "checkinsCount":4063
            },
            "url":"http:\/\/elmcoffeeroasters.com",
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"55fc6351498e081c6ae9a9c1",
            "name":"Slate Coffee",
            "contact":{
               "twitter":"slatecoffee"
            },
            "location":{
               "address":"602 2nd Ave",
               "crossStreet":"James St",
               "lat":47.60226958101576,
               "lng":-122.33254930945151,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.60226958101576,
                     "lng":-122.33254930945151
                  }
               ],
               "postalCode":"98104",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "602 2nd Ave (James St)",
                  "Seattle, WA 98104",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":false,
            "stats":{
               "tipCount":23,
               "usersCount":556,
               "checkinsCount":1296
            },
            "url":"http:\/\/slatecoffee.com",
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"569d5c6c498e4ff52aa8b724",
            "name":"Olympia Coffee Roasters",
            "contact":{

            },
            "location":{
               "address":"2021 7th Ave",
               "lat":47.615100389907994,
               "lng":-122.3383441043283,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.615100389907994,
                     "lng":-122.3383441043283
                  }
               ],
               "postalCode":"98121",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "2021 7th Ave",
                  "Seattle, WA 98121",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":false,
            "stats":{
               "tipCount":4,
               "usersCount":150,
               "checkinsCount":1120
            },
            "url":"http:\/\/amazon.cafebonappetit.com\/cafe\/olympia-coffee-roasters\/",
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"4a609aa8f964a520ebc01fe3",
            "name":"Pegasus Coffee",
            "contact":{
               "phone":"2066823113",
               "formattedPhone":"(206) 682-3113"
            },
            "location":{
               "address":"711 3rd Ave",
               "crossStreet":"at Cherry St",
               "lat":47.603689,
               "lng":-122.332502,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.603689,
                     "lng":-122.332502
                  }
               ],
               "postalCode":"98104",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "711 3rd Ave (at Cherry St)",
                  "Seattle, WA 98104",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":true,
            "stats":{
               "tipCount":15,
               "usersCount":485,
               "checkinsCount":2910
            },
            "url":"http:\/\/pegasuscoffeehouse.com",
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"4a53845cf964a5205eb21fe3",
            "name":"Tully's Coffee",
            "contact":{
               "phone":"2063820533",
               "formattedPhone":"(206) 382-0533"
            },
            "location":{
               "address":"821 2nd Ave Ste 402",
               "crossStreet":"btw Marion & Columbia",
               "lat":47.604219783711095,
               "lng":-122.3346137579619,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.604219783711095,
                     "lng":-122.3346137579619
                  }
               ],
               "postalCode":"98104",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "821 2nd Ave Ste 402 (btw Marion & Columbia)",
                  "Seattle, WA 98104",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":true,
            "stats":{
               "tipCount":7,
               "usersCount":495,
               "checkinsCount":2991
            },
            "url":"http:\/\/tullyscoffeeshops.com",
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "storeId":"1088",
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[
               {
                  "id":"5569f401a7c8896abe7c73c8"
               }
            ],
            "hasPerk":false
         },
         {
            "id":"4a848900f964a520e3fc1fe3",
            "name":"Cherry Street Coffee House",
            "contact":{
               "phone":"2064429372",
               "formattedPhone":"(206) 442-9372",
               "twitter":"cherrystreet"
            },
            "location":{
               "address":"808 3rd Ave",
               "crossStreet":"btw Marion & Columbia",
               "lat":47.60451120781553,
               "lng":-122.3330104220454,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.60451120781553,
                     "lng":-122.3330104220454
                  }
               ],
               "postalCode":"98104",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "808 3rd Ave (btw Marion & Columbia)",
                  "Seattle, WA 98104",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":true,
            "stats":{
               "tipCount":13,
               "usersCount":673,
               "checkinsCount":2296
            },
            "url":"http:\/\/www.cherrybaba.com",
            "hasMenu":true,
            "menu":{
               "type":"Menu",
               "label":"Menu",
               "anchor":"View Menu",
               "url":"https:\/\/foursquare.com\/v\/cherry-street-coffee-house\/4a848900f964a520e3fc1fe3\/menu",
               "mobileUrl":"https:\/\/foursquare.com\/v\/4a848900f964a520e3fc1fe3\/device_menu"
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"475ebc58f964a520d94c1fe3",
            "name":"Kaladi Brothers Coffee",
            "contact":{
               "phone":"2063881700",
               "formattedPhone":"(206) 388-1700",
               "twitter":"kbcseattle"
            },
            "location":{
               "address":"517 E Pike St",
               "crossStreet":"at Belmont Ave.",
               "lat":47.61415161351147,
               "lng":-122.32456505977603,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.61415161351147,
                     "lng":-122.32456505977603
                  }
               ],
               "postalCode":"98122",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "517 E Pike St (at Belmont Ave.)",
                  "Seattle, WA 98122",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":false,
            "stats":{
               "tipCount":38,
               "usersCount":1667,
               "checkinsCount":5090
            },
            "url":"http:\/\/www.kaladi.com",
            "hasMenu":true,
            "menu":{
               "type":"Menu",
               "label":"Menu",
               "anchor":"View Menu",
               "url":"https:\/\/foursquare.com\/v\/kaladi-brothers-coffee\/475ebc58f964a520d94c1fe3\/menu",
               "mobileUrl":"https:\/\/foursquare.com\/v\/475ebc58f964a520d94c1fe3\/device_menu"
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "storeId":"",
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"4aa1a711f964a520684120e3",
            "name":"Cherry Street Coffee House",
            "contact":{
               "phone":"2064417176",
               "formattedPhone":"(206) 441-7176",
               "twitter":"cherrystreet"
            },
            "location":{
               "address":"2121 1st Ave",
               "crossStreet":"Btw Blanchard & Lenora St.",
               "lat":47.61224159203839,
               "lng":-122.34474021390412,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.61224159203839,
                     "lng":-122.34474021390412
                  }
               ],
               "postalCode":"98121",
               "cc":"US",
               "neighborhood":"Belltown",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "2121 1st Ave (Btw Blanchard & Lenora St.)",
                  "Seattle, WA 98121",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":false,
            "stats":{
               "tipCount":30,
               "usersCount":1649,
               "checkinsCount":4794
            },
            "url":"http:\/\/cherryst.com",
            "hasMenu":true,
            "menu":{
               "type":"Menu",
               "label":"Menu",
               "anchor":"View Menu",
               "url":"https:\/\/foursquare.com\/v\/cherry-street-coffee-house\/4aa1a711f964a520684120e3\/menu",
               "mobileUrl":"https:\/\/foursquare.com\/v\/4aa1a711f964a520684120e3\/device_menu"
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":1,
               "summary":"One other person is here",
               "groups":[
                  {
                     "type":"others",
                     "name":"Other people here",
                     "count":1,
                     "items":[

                     ]
                  }
               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"4412e177f964a520db301fe3",
            "name":"Panama Hotel Tea & Coffee",
            "contact":{
               "phone":"2065154000",
               "formattedPhone":"(206) 515-4000"
            },
            "location":{
               "address":"607 S Main St",
               "crossStreet":"btwn 6th & Maynard Ave. S",
               "lat":47.59997006448296,
               "lng":-122.32614684210247,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.59997006448296,
                     "lng":-122.32614684210247
                  }
               ],
               "postalCode":"98104",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "607 S Main St (btwn 6th & Maynard Ave. S)",
                  "Seattle, WA 98104",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":false,
            "stats":{
               "tipCount":15,
               "usersCount":846,
               "checkinsCount":1514
            },
            "url":"http:\/\/www.panamahotel.net\/teahouse.htm",
            "hasMenu":true,
            "menu":{
               "type":"Menu",
               "label":"Menu",
               "anchor":"View Menu",
               "url":"https:\/\/foursquare.com\/v\/panama-hotel-tea--coffee\/4412e177f964a520db301fe3\/menu",
               "mobileUrl":"https:\/\/foursquare.com\/v\/4412e177f964a520db301fe3\/device_menu"
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"4b5daa3ff964a520cc6529e3",
            "name":"Pegasus Coffee",
            "contact":{
               "phone":"2062923013",
               "formattedPhone":"(206) 292-3013"
            },
            "location":{
               "address":"1218 3rd Ave",
               "crossStreet":"at Seneca St",
               "lat":47.60755521415362,
               "lng":-122.33584527606352,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.60755521415362,
                     "lng":-122.33584527606352
                  }
               ],
               "postalCode":"98101",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "1218 3rd Ave (at Seneca St)",
                  "Seattle, WA 98101",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":false,
            "stats":{
               "tipCount":6,
               "usersCount":278,
               "checkinsCount":1546
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"4a26f5c5f964a520f47e1fe3",
            "name":"Bedlam Coffee",
            "contact":{
               "phone":"2069102300",
               "formattedPhone":"(206) 910-2300",
               "twitter":"bedlamcoffee",
               "facebook":"117036506160",
               "facebookUsername":"BedlamCoffee",
               "facebookName":"Bedlam Coffee"
            },
            "location":{
               "address":"2231 2nd Ave",
               "crossStreet":"Bell St",
               "lat":47.613948460584,
               "lng":-122.34548328955584,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.613948460584,
                     "lng":-122.34548328955584
                  }
               ],
               "postalCode":"98121",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "2231 2nd Ave (Bell St)",
                  "Seattle, WA 98121",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":true,
            "stats":{
               "tipCount":85,
               "usersCount":2538,
               "checkinsCount":8680
            },
            "url":"http:\/\/bedlamcoffee.com",
            "hasMenu":true,
            "menu":{
               "type":"Menu",
               "label":"Menu",
               "anchor":"View Menu",
               "url":"https:\/\/foursquare.com\/v\/bedlam-coffee\/4a26f5c5f964a520f47e1fe3\/menu",
               "mobileUrl":"https:\/\/foursquare.com\/v\/4a26f5c5f964a520f47e1fe3\/device_menu"
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "venuePage":{
               "id":"89452925"
            },
            "storeId":"",
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"4a63a829f964a52087c51fe3",
            "name":"Cupcake Royale and Vérité Coffee",
            "contact":{
               "phone":"2067019579",
               "formattedPhone":"(206) 701-9579",
               "twitter":"cupcakeroyale",
               "facebook":"145697968787117",
               "facebookUsername":"CupcakeRoyaleCapitolHill",
               "facebookName":"Cupcake Royale"
            },
            "location":{
               "address":"1111 E Pike St",
               "crossStreet":"btwn 11th & 12th Ave",
               "lat":47.614013174009195,
               "lng":-122.31760626759302,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.614013174009195,
                     "lng":-122.31760626759302
                  }
               ],
               "postalCode":"98122",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "1111 E Pike St (btwn 11th & 12th Ave)",
                  "Seattle, WA 98122",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1bc941735",
                  "name":"Cupcake Shop",
                  "pluralName":"Cupcake Shops",
                  "shortName":"Cupcakes",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/cupcakes_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":true,
            "stats":{
               "tipCount":91,
               "usersCount":4472,
               "checkinsCount":9623
            },
            "url":"http:\/\/cupcakeroyale.com\/",
            "hasMenu":true,
            "menu":{
               "type":"Menu",
               "label":"Menu",
               "anchor":"View Menu",
               "url":"https:\/\/foursquare.com\/v\/cupcake-royale-and-v%C3%A9rit%C3%A9-coffee\/4a63a829f964a52087c51fe3\/menu",
               "mobileUrl":"https:\/\/foursquare.com\/v\/4a63a829f964a52087c51fe3\/device_menu"
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "storeId":"",
            "hereNow":{
               "count":1,
               "summary":"One other person is here",
               "groups":[
                  {
                     "type":"others",
                     "name":"Other people here",
                     "count":1,
                     "items":[

                     ]
                  }
               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[
               {
                  "id":"5568eddda7c8a9cf8ec3b92e"
               }
            ],
            "hasPerk":false
         },
         {
            "id":"4a7b455ef964a52089ea1fe3",
            "name":"Stumptown Coffee Roasters",
            "contact":{
               "phone":"2063231544",
               "formattedPhone":"(206) 323-1544",
               "twitter":"stumptowncoffee"
            },
            "location":{
               "address":"1115 12th Ave",
               "crossStreet":"at Spring St",
               "lat":47.61203641962361,
               "lng":-122.31700301170349,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.61203641962361,
                     "lng":-122.31700301170349
                  }
               ],
               "postalCode":"98122",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "1115 12th Ave (at Spring St)",
                  "Seattle, WA 98122",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":true,
            "stats":{
               "tipCount":78,
               "usersCount":3448,
               "checkinsCount":11631
            },
            "url":"http:\/\/t.co\/HP1jMKlOZf",
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[
               {
                  "id":"556f4246bd6a007c77387d91"
               }
            ],
            "hasPerk":false
         },
         {
            "id":"5802b14d38fa7d4a74864fe9",
            "name":"Urban Coffee House",
            "contact":{

            },
            "location":{
               "address":"1900 4th Ave",
               "lat":47.612412527281144,
               "lng":-122.3386644359043,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.612412527281144,
                     "lng":-122.3386644359043
                  }
               ],
               "postalCode":"98101",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "1900 4th Ave",
                  "Seattle, WA 98101",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":false,
            "stats":{
               "tipCount":0,
               "usersCount":86,
               "checkinsCount":207
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"509a9305e4b05e3770ebe234",
            "name":"Rococo Coffee Roasting",
            "contact":{
               "phone":"4258039081",
               "formattedPhone":"(425) 803-9081"
            },
            "location":{
               "address":"207 Boren Ave N",
               "crossStreet":"John And Boren N",
               "lat":47.62023771347799,
               "lng":-122.33598581355247,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.62023771347799,
                     "lng":-122.33598581355247
                  }
               ],
               "postalCode":"98109",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "207 Boren Ave N (John And Boren N)",
                  "Seattle, WA 98109",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":false,
            "stats":{
               "tipCount":17,
               "usersCount":226,
               "checkinsCount":2216
            },
            "url":"http:\/\/rocococoffee.com",
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":1,
               "summary":"One other person is here",
               "groups":[
                  {
                     "type":"others",
                     "name":"Other people here",
                     "count":1,
                     "items":[

                     ]
                  }
               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         },
         {
            "id":"49de6c3df964a5204e601fe3",
            "name":"Cherry Street Coffee House",
            "contact":{
               "phone":"2064415489",
               "formattedPhone":"(206) 441-5489",
               "twitter":"cherrystreet"
            },
            "location":{
               "address":"2719 1st Ave",
               "crossStreet":"at Clay St",
               "lat":47.61626578219188,
               "lng":-122.35156979634606,
               "labeledLatLngs":[
                  {
                     "label":"display",
                     "lat":47.61626578219188,
                     "lng":-122.35156979634606
                  }
               ],
               "postalCode":"98121",
               "cc":"US",
               "city":"Seattle",
               "state":"WA",
               "country":"United States",
               "formattedAddress":[
                  "2719 1st Ave (at Clay St)",
                  "Seattle, WA 98121",
                  "United States"
               ]
            },
            "categories":[
               {
                  "id":"4bf58dd8d48988d1e0931735",
                  "name":"Coffee Shop",
                  "pluralName":"Coffee Shops",
                  "shortName":"Coffee Shop",
                  "icon":{
                     "prefix":"https:\/\/ss3.4sqi.net\/img\/categories_v2\/food\/coffeeshop_",
                     "suffix":".png"
                  },
                  "primary":true
               }
            ],
            "verified":false,
            "stats":{
               "tipCount":47,
               "usersCount":1403,
               "checkinsCount":6402
            },
            "hasMenu":true,
            "menu":{
               "type":"Menu",
               "label":"Menu",
               "anchor":"View Menu",
               "url":"https:\/\/foursquare.com\/v\/cherry-street-coffee-house\/49de6c3df964a5204e601fe3\/menu",
               "mobileUrl":"https:\/\/foursquare.com\/v\/49de6c3df964a5204e601fe3\/device_menu"
            },
            "allowMenuUrlEdit":true,
            "beenHere":{
               "lastCheckinExpiredAt":0
            },
            "specials":{
               "count":0,
               "items":[

               ]
            },
            "hereNow":{
               "count":0,
               "summary":"Nobody here",
               "groups":[

               ]
            },
            "referralId":"v-1523913911",
            "venueChains":[

            ],
            "hasPerk":false
         }
      ],
      "geocode":{
         "what":"",
         "where":"seattle wa",
         "feature":{
            "cc":"US",
            "name":"Seattle",
            "displayName":"Seattle, WA, United States",
            "matchedName":"Seattle, WA, United States",
            "highlightedName":"<b>Seattle<\/b>, <b>WA<\/b>, United States",
            "woeType":7,
            "slug":"seattle-washington",
            "id":"geonameid:5809844",
            "longId":"72057594043737780",
            "geometry":{
               "center":{
                  "lat":47.60621,
                  "lng":-122.33207
               },
               "bounds":{
                  "ne":{
                     "lat":47.734145,
                     "lng":-122.224433
                  },
                  "sw":{
                     "lat":47.481719999999996,
                     "lng":-122.459696
                  }
               }
            }
         },
         "parents":[

         ]
      }
   }
}
```
