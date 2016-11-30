## HomeAway Coding Challenge 

To assist in gaining an understanding about how the candidate thinks about code. 

#### Summary

Write a type ahead against the Seat Geek API. The type ahead should update a list of results as the search query changes. Results can be tapped to view them on a details screen. On the details screen the result can be favorited. Upon doing new type ahead queries, if results that have already been favorited have been returned, they should indicate that they were favorited. 

To summarize

1. Write a type ahead against the Seat Geek API
2. Make a detail screen so the user can drill down into a result
3. The detail screen should allow the user to favorite the event
4. Type ahead results should contain an indication if they had been favorited previously
5. Favorited results should be saved between launches of the app 

The two screens can look similar to these:

![potential design](https://dl.dropboxusercontent.com/u/13776061/Screen%20Shot%202016-07-15%20at%209.48.15%20AM.png)

The coding challenge will be judged on

1. Attention to detail
2. Architectural choices
3. Knowledge of Android libraries and SDKs 

An adequate solution might be developed within 4 - 8 hours, but please spend however much time it takes to construct a great solution. 

#### API Information 

The endpoint to use on Seat Geek is a pulbic endpoint. You will pass in the url param of `q` which will correspond to the search query. For example, the below query will give a result set for the term `Texas Ranger`. 

```
https://api.seatgeek.com/2/events?q=Texas+Ranger
```

The resulting json from `Texas Ranger` might look like

```
{
	"meta": {
		"per_page": 10,
		"total": 19,
		"page": 1,
		"geolocation": null
	},
	"events": [{
		"links": [],
		"id": 2930972,
		"stats": {
			"listing_count": 192,
			"average_price": 26.5,
			"lowest_price_good_deals": 8.0,
			"lowest_price": 8.0,
			"highest_price": 47.0
		},
		"title": "Texas Rangers at Oakland Athletics",
		"announce_date": "2015-11-17T00:00:00",
		"score": 0.689314,
		"date_tbd": false,
		"type": "mlb",
		"datetime_local": "2016-06-13T19:05:00",
		"visible_until_utc": "2016-06-14T06:05:00",
		"time_tbd": false,
		"taxonomies": [{
			"parent_id": null,
			"id": 1000000,
			"name": "sports"
		}, {
			"parent_id": 1000000,
			"id": 1010000,
			"name": "baseball"
		}, {
			"parent_id": 1010000,
			"id": 1010100,
			"name": "mlb"
		}],
		"performers": [{
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/oakland-athletics-c4a159\/14\/huge.jpg",
			"primary": true,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/oakland-athletics-c4a159\/14\/huge.jpg"
			},
			"has_upcoming_events": true,
			"id": 14,
			"stats": {
				"event_count": 101
			},
			"score": 0.65348,
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"type": "mlb",
			"short_name": "Athletics",
			"home_venue_id": 14,
			"slug": "oakland-athletics",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"home_team": true,
			"name": "Oakland Athletics",
			"url": "https:\/\/seatgeek.com\/oakland-athletics-tickets"
		}, {
			"away_team": true,
			"stats": {
				"event_count": 100
			},
			"name": "Texas Rangers",
			"short_name": "Rangers",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"url": "https:\/\/seatgeek.com\/texas-rangers-tickets",
			"type": "mlb",
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg",
			"home_venue_id": 16,
			"slug": "texas-rangers",
			"score": 0.743116,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg"
			},
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"has_upcoming_events": true,
			"id": 16
		}],
		"url": "https:\/\/seatgeek.com\/rangers-at-athletics-tickets\/6-13-2016-oakland-california-oakland-coliseum\/mlb\/2930972",
		"created_at": "2015-11-17T00:00:00",
		"venue": {
			"city": "Oakland",
			"name": "Oakland Coliseum",
			"extended_address": "Oakland, CA 94621",
			"url": "https:\/\/seatgeek.com\/venues\/oakland-coliseum\/tickets",
			"country": "US",
			"display_location": "Oakland, CA",
			"links": [],
			"slug": "oakland-coliseum",
			"state": "CA",
			"score": 0.794667,
			"postal_code": "94621",
			"location": {
				"lat": 37.7469,
				"lon": -122.201
			},
			"address": "7000 Coliseum Way",
			"timezone": "America\/Los_Angeles",
			"id": 14
		},
		"short_title": "Rangers at Athletics",
		"datetime_utc": "2016-06-14T02:05:00",
		"datetime_tbd": false
	}, {
		"links": [],
		"id": 2932574,
		"stats": {
			"listing_count": 2298,
			"average_price": 74.0,
			"lowest_price_good_deals": 27.0,
			"lowest_price": 27.0,
			"highest_price": 570.0
		},
		"title": "Texas Rangers at St. Louis Cardinals",
		"announce_date": "2015-11-17T00:00:00",
		"score": 0.779175,
		"date_tbd": false,
		"type": "mlb",
		"datetime_local": "2016-06-18T15:10:00",
		"visible_until_utc": "2016-06-19T00:10:00",
		"time_tbd": false,
		"taxonomies": [{
			"parent_id": null,
			"id": 1000000,
			"name": "sports"
		}, {
			"parent_id": 1000000,
			"id": 1010000,
			"name": "baseball"
		}, {
			"parent_id": 1010000,
			"id": 1010100,
			"name": "mlb"
		}],
		"performers": [{
			"away_team": true,
			"stats": {
				"event_count": 100
			},
			"name": "Texas Rangers",
			"short_name": "Rangers",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"url": "https:\/\/seatgeek.com\/texas-rangers-tickets",
			"type": "mlb",
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg",
			"home_venue_id": 16,
			"slug": "texas-rangers",
			"score": 0.743116,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg"
			},
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"has_upcoming_events": true,
			"id": 16
		}, {
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/st-louis-cardinals-a9b127\/27\/huge.jpg",
			"primary": true,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/st-louis-cardinals-a9b127\/27\/huge.jpg"
			},
			"has_upcoming_events": true,
			"id": 27,
			"stats": {
				"event_count": 100
			},
			"score": 0.747909,
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"type": "mlb",
			"short_name": "Cardinals",
			"home_venue_id": 27,
			"slug": "st-louis-cardinals",
			"divisions": [{
				"display_name": "National League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "National League Central",
				"short_name": "NL Central",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "national-league-central"
			}],
			"home_team": true,
			"name": "St. Louis Cardinals",
			"url": "https:\/\/seatgeek.com\/st-louis-cardinals-tickets"
		}],
		"url": "https:\/\/seatgeek.com\/rangers-at-cardinals-tickets\/6-18-2016-st-louis-missouri-busch-stadium\/mlb\/2932574",
		"created_at": "2015-11-17T00:00:00",
		"venue": {
			"city": "St. Louis",
			"name": "Busch Stadium",
			"extended_address": "St. Louis, MO 63102",
			"url": "https:\/\/seatgeek.com\/venues\/busch-stadium\/tickets",
			"country": "US",
			"display_location": "St. Louis, MO",
			"links": [],
			"slug": "busch-stadium",
			"state": "MO",
			"score": 0.866628,
			"postal_code": "63102",
			"location": {
				"lat": 38.6226,
				"lon": -90.1928
			},
			"address": "700 Clark Street",
			"timezone": "America\/Chicago",
			"id": 27
		},
		"short_title": "Rangers at Cardinals",
		"datetime_utc": "2016-06-18T20:10:00",
		"datetime_tbd": false
	}, {
		"links": [],
		"id": 2931982,
		"stats": {
			"listing_count": 2165,
			"average_price": 113.0,
			"lowest_price_good_deals": 24.0,
			"lowest_price": 24.0,
			"highest_price": 7752.0
		},
		"title": "Boston Red Sox at Texas Rangers",
		"announce_date": "2015-11-17T00:00:00",
		"score": 0.78381,
		"date_tbd": false,
		"type": "mlb",
		"datetime_local": "2016-06-25T20:20:00",
		"visible_until_utc": "2016-06-26T05:20:00",
		"time_tbd": false,
		"taxonomies": [{
			"parent_id": null,
			"id": 1000000,
			"name": "sports"
		}, {
			"parent_id": 1000000,
			"id": 1010000,
			"name": "baseball"
		}, {
			"parent_id": 1010000,
			"id": 1010100,
			"name": "mlb"
		}],
		"performers": [{
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg",
			"primary": true,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg"
			},
			"has_upcoming_events": true,
			"id": 16,
			"stats": {
				"event_count": 100
			},
			"score": 0.743116,
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"type": "mlb",
			"short_name": "Rangers",
			"home_venue_id": 16,
			"slug": "texas-rangers",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"home_team": true,
			"name": "Texas Rangers",
			"url": "https:\/\/seatgeek.com\/texas-rangers-tickets"
		}, {
			"away_team": true,
			"stats": {
				"event_count": 101
			},
			"name": "Boston Red Sox",
			"short_name": "Red Sox",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League East",
				"short_name": "AL East",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-east"
			}],
			"url": "https:\/\/seatgeek.com\/boston-red-sox-tickets",
			"type": "mlb",
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/boston-red-sox-deafb0\/21\/huge.jpg",
			"home_venue_id": 21,
			"slug": "boston-red-sox",
			"score": 0.772448,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/boston-red-sox-deafb0\/21\/huge.jpg"
			},
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"has_upcoming_events": true,
			"id": 21
		}],
		"url": "https:\/\/seatgeek.com\/red-sox-at-rangers-tickets\/6-25-2016-arlington-texas-globe-life-park\/mlb\/2931982",
		"created_at": "2015-11-17T00:00:00",
		"venue": {
			"city": "Arlington",
			"name": "Globe Life Park",
			"extended_address": "Arlington, TX 76011",
			"url": "https:\/\/seatgeek.com\/venues\/globe-life-park\/tickets",
			"country": "US",
			"display_location": "Arlington, TX",
			"links": [],
			"slug": "globe-life-park",
			"state": "TX",
			"score": 0.861761,
			"postal_code": "76011",
			"location": {
				"lat": 32.7506,
				"lon": -97.0824
			},
			"address": "1000 Ballpark Way",
			"timezone": "America\/Chicago",
			"id": 16
		},
		"short_title": "Red Sox at Rangers",
		"datetime_utc": "2016-06-26T01:20:00",
		"datetime_tbd": false
	}, {
		"links": [],
		"id": 2932384,
		"stats": {
			"listing_count": 3157,
			"average_price": 68.0,
			"lowest_price_good_deals": 15.0,
			"lowest_price": 15.0,
			"highest_price": 1558.0
		},
		"title": "Texas Rangers at New York Yankees",
		"announce_date": "2015-11-17T00:00:00",
		"score": 0.807885,
		"date_tbd": false,
		"type": "mlb",
		"datetime_local": "2016-06-30T13:05:00",
		"visible_until_utc": "2016-06-30T21:05:00",
		"time_tbd": false,
		"taxonomies": [{
			"parent_id": null,
			"id": 1000000,
			"name": "sports"
		}, {
			"parent_id": 1000000,
			"id": 1010000,
			"name": "baseball"
		}, {
			"parent_id": 1010000,
			"id": 1010100,
			"name": "mlb"
		}],
		"performers": [{
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/new-york-yankees-4591da\/8\/huge.jpg",
			"primary": true,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/new-york-yankees-4591da\/8\/huge.jpg"
			},
			"has_upcoming_events": true,
			"id": 8,
			"stats": {
				"event_count": 100
			},
			"score": 0.78616,
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"type": "mlb",
			"short_name": "Yankees",
			"home_venue_id": 8,
			"slug": "new-york-yankees",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League East",
				"short_name": "AL East",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-east"
			}],
			"home_team": true,
			"name": "New York Yankees",
			"url": "https:\/\/seatgeek.com\/new-york-yankees-tickets"
		}, {
			"away_team": true,
			"stats": {
				"event_count": 100
			},
			"name": "Texas Rangers",
			"short_name": "Rangers",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"url": "https:\/\/seatgeek.com\/texas-rangers-tickets",
			"type": "mlb",
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg",
			"home_venue_id": 16,
			"slug": "texas-rangers",
			"score": 0.743116,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg"
			},
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"has_upcoming_events": true,
			"id": 16
		}],
		"url": "https:\/\/seatgeek.com\/rangers-at-yankees-tickets\/6-30-2016-bronx-new-york-yankee-stadium\/mlb\/2932384",
		"created_at": "2015-11-17T00:00:00",
		"venue": {
			"city": "Bronx",
			"name": "Yankee Stadium",
			"extended_address": "Bronx, NY 10451",
			"url": "https:\/\/seatgeek.com\/venues\/yankee-stadium\/tickets",
			"country": "US",
			"display_location": "Bronx, NY",
			"links": [],
			"slug": "yankee-stadium",
			"state": "NY",
			"score": 0.91087,
			"postal_code": "10451",
			"location": {
				"lat": 40.8288,
				"lon": -73.9266
			},
			"address": "1 East 161st Street",
			"timezone": "America\/New_York",
			"id": 8
		},
		"short_title": "Rangers at Yankees",
		"datetime_utc": "2016-06-30T17:05:00",
		"datetime_tbd": false
	}, {
		"links": [],
		"id": 2932702,
		"stats": {
			"listing_count": 1414,
			"average_price": 72.0,
			"lowest_price_good_deals": 13.0,
			"lowest_price": 13.0,
			"highest_price": 732.0
		},
		"title": "Texas Rangers at Minnesota Twins",
		"announce_date": "2015-11-17T00:00:00",
		"score": 0.734112,
		"date_tbd": false,
		"type": "mlb",
		"datetime_local": "2016-07-01T19:10:00",
		"visible_until_utc": "2016-07-02T04:10:00",
		"time_tbd": false,
		"taxonomies": [{
			"parent_id": null,
			"id": 1000000,
			"name": "sports"
		}, {
			"parent_id": 1000000,
			"id": 1010000,
			"name": "baseball"
		}, {
			"parent_id": 1010000,
			"id": 1010100,
			"name": "mlb"
		}],
		"performers": [{
			"away_team": true,
			"stats": {
				"event_count": 100
			},
			"name": "Texas Rangers",
			"short_name": "Rangers",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"url": "https:\/\/seatgeek.com\/texas-rangers-tickets",
			"type": "mlb",
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg",
			"home_venue_id": 16,
			"slug": "texas-rangers",
			"score": 0.743116,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg"
			},
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"has_upcoming_events": true,
			"id": 16
		}, {
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/minnesota-twins-ee707f\/19\/huge.jpg",
			"primary": true,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/minnesota-twins-ee707f\/19\/huge.jpg"
			},
			"has_upcoming_events": true,
			"id": 19,
			"stats": {
				"event_count": 101
			},
			"score": 0.699819,
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"type": "mlb",
			"short_name": "Twins",
			"home_venue_id": 3712,
			"slug": "minnesota-twins",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League Central",
				"short_name": "AL Central",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-central"
			}],
			"home_team": true,
			"name": "Minnesota Twins",
			"url": "https:\/\/seatgeek.com\/minnesota-twins-tickets"
		}],
		"url": "https:\/\/seatgeek.com\/rangers-at-twins-tickets\/7-1-2016-minneapolis-minnesota-target-field\/mlb\/2932702",
		"created_at": "2015-11-17T00:00:00",
		"venue": {
			"city": "Minneapolis",
			"name": "Target Field",
			"extended_address": "Minneapolis, MN 55403",
			"url": "https:\/\/seatgeek.com\/venues\/target-field\/tickets",
			"country": "US",
			"display_location": "Minneapolis, MN",
			"links": [],
			"slug": "target-field",
			"state": "MN",
			"score": 0.816663,
			"postal_code": "55403",
			"location": {
				"lat": 44.9807,
				"lon": -93.2786
			},
			"address": "1 Twins Way",
			"timezone": "America\/Chicago",
			"id": 3712
		},
		"short_title": "Rangers at Twins",
		"datetime_utc": "2016-07-02T00:10:00",
		"datetime_tbd": false
	}, {
		"links": [],
		"id": 2932175,
		"stats": {
			"listing_count": 2088,
			"average_price": 175.0,
			"lowest_price_good_deals": 75.0,
			"lowest_price": 75.0,
			"highest_price": 3162.0
		},
		"title": "Texas Rangers at Chicago Cubs",
		"announce_date": "2015-11-17T00:00:00",
		"score": 0.786512,
		"date_tbd": false,
		"type": "mlb",
		"datetime_local": "2016-07-16T13:20:00",
		"visible_until_utc": "2016-07-16T22:20:00",
		"time_tbd": false,
		"taxonomies": [{
			"parent_id": null,
			"id": 1000000,
			"name": "sports"
		}, {
			"parent_id": 1000000,
			"id": 1010000,
			"name": "baseball"
		}, {
			"parent_id": 1010000,
			"id": 1010100,
			"name": "mlb"
		}],
		"performers": [{
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/chicago-cubs-ab72e2\/11\/huge.jpg",
			"primary": true,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/chicago-cubs-ab72e2\/11\/huge.jpg"
			},
			"has_upcoming_events": true,
			"id": 11,
			"stats": {
				"event_count": 102
			},
			"score": 0.741513,
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"type": "mlb",
			"short_name": "Cubs",
			"home_venue_id": 11,
			"slug": "chicago-cubs",
			"divisions": [{
				"display_name": "National League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "National League Central",
				"short_name": "NL Central",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "national-league-central"
			}],
			"home_team": true,
			"name": "Chicago Cubs",
			"url": "https:\/\/seatgeek.com\/chicago-cubs-tickets"
		}, {
			"away_team": true,
			"stats": {
				"event_count": 100
			},
			"name": "Texas Rangers",
			"short_name": "Rangers",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"url": "https:\/\/seatgeek.com\/texas-rangers-tickets",
			"type": "mlb",
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg",
			"home_venue_id": 16,
			"slug": "texas-rangers",
			"score": 0.743116,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg"
			},
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"has_upcoming_events": true,
			"id": 16
		}],
		"url": "https:\/\/seatgeek.com\/rangers-at-cubs-tickets\/7-16-2016-chicago-illinois-wrigley-field\/mlb\/2932175",
		"created_at": "2015-11-17T00:00:00",
		"venue": {
			"city": "Chicago",
			"name": "Wrigley Field",
			"extended_address": "Chicago, IL 60613",
			"url": "https:\/\/seatgeek.com\/venues\/wrigley-field\/tickets",
			"country": "US",
			"display_location": "Chicago, IL",
			"links": [],
			"slug": "wrigley-field",
			"state": "IL",
			"score": 0.865311,
			"postal_code": "60613",
			"location": {
				"lat": 41.9474,
				"lon": -87.6566
			},
			"address": "1060 West Addison Street",
			"timezone": "America\/Chicago",
			"id": 11
		},
		"short_title": "Rangers at Cubs",
		"datetime_utc": "2016-07-16T18:20:00",
		"datetime_tbd": false
	}, {
		"links": [],
		"id": 2931975,
		"stats": {
			"listing_count": 2881,
			"average_price": 42.0,
			"lowest_price_good_deals": 7.0,
			"lowest_price": 7.0,
			"highest_price": 5372.0
		},
		"title": "Oakland Athletics at Texas Rangers",
		"announce_date": "2015-11-17T00:00:00",
		"score": 0.771358,
		"date_tbd": false,
		"type": "mlb",
		"datetime_local": "2016-07-26T19:05:00",
		"visible_until_utc": "2016-07-27T04:05:00",
		"time_tbd": false,
		"taxonomies": [{
			"parent_id": null,
			"id": 1000000,
			"name": "sports"
		}, {
			"parent_id": 1000000,
			"id": 1010000,
			"name": "baseball"
		}, {
			"parent_id": 1010000,
			"id": 1010100,
			"name": "mlb"
		}],
		"performers": [{
			"away_team": true,
			"stats": {
				"event_count": 101
			},
			"name": "Oakland Athletics",
			"short_name": "Athletics",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"url": "https:\/\/seatgeek.com\/oakland-athletics-tickets",
			"type": "mlb",
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/oakland-athletics-c4a159\/14\/huge.jpg",
			"home_venue_id": 14,
			"slug": "oakland-athletics",
			"score": 0.65348,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/oakland-athletics-c4a159\/14\/huge.jpg"
			},
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"has_upcoming_events": true,
			"id": 14
		}, {
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg",
			"primary": true,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg"
			},
			"has_upcoming_events": true,
			"id": 16,
			"stats": {
				"event_count": 100
			},
			"score": 0.743116,
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"type": "mlb",
			"short_name": "Rangers",
			"home_venue_id": 16,
			"slug": "texas-rangers",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"home_team": true,
			"name": "Texas Rangers",
			"url": "https:\/\/seatgeek.com\/texas-rangers-tickets"
		}],
		"url": "https:\/\/seatgeek.com\/athletics-at-rangers-tickets\/7-26-2016-arlington-texas-globe-life-park\/mlb\/2931975",
		"created_at": "2015-11-17T00:00:00",
		"venue": {
			"city": "Arlington",
			"name": "Globe Life Park",
			"extended_address": "Arlington, TX 76011",
			"url": "https:\/\/seatgeek.com\/venues\/globe-life-park\/tickets",
			"country": "US",
			"display_location": "Arlington, TX",
			"links": [],
			"slug": "globe-life-park",
			"state": "TX",
			"score": 0.861761,
			"postal_code": "76011",
			"location": {
				"lat": 32.7506,
				"lon": -97.0824
			},
			"address": "1000 Ballpark Way",
			"timezone": "America\/Chicago",
			"id": 16
		},
		"short_title": "Athletics at Rangers",
		"datetime_utc": "2016-07-27T00:05:00",
		"datetime_tbd": false
	}, {
		"links": [],
		"id": 2931970,
		"stats": {
			"listing_count": 2583,
			"average_price": 59.0,
			"lowest_price_good_deals": 10.0,
			"lowest_price": 10.0,
			"highest_price": 975.0
		},
		"title": "Kansas City Royals at Texas Rangers",
		"announce_date": "2015-11-17T00:00:00",
		"score": 0.768381,
		"date_tbd": false,
		"type": "mlb",
		"datetime_local": "2016-07-31T14:05:00",
		"visible_until_utc": "2016-07-31T23:05:00",
		"time_tbd": false,
		"taxonomies": [{
			"parent_id": null,
			"id": 1000000,
			"name": "sports"
		}, {
			"parent_id": 1000000,
			"id": 1010000,
			"name": "baseball"
		}, {
			"parent_id": 1010000,
			"id": 1010100,
			"name": "mlb"
		}],
		"performers": [{
			"away_team": true,
			"stats": {
				"event_count": 101
			},
			"name": "Kansas City Royals",
			"short_name": "Royals",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League Central",
				"short_name": "AL Central",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-central"
			}],
			"url": "https:\/\/seatgeek.com\/kansas-city-royals-tickets",
			"type": "mlb",
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/kansas-city-royals-3df70f\/5\/huge.jpg",
			"home_venue_id": 3714,
			"slug": "kansas-city-royals",
			"score": 0.719098,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/kansas-city-royals-3df70f\/5\/huge.jpg"
			},
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"has_upcoming_events": true,
			"id": 5
		}, {
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg",
			"primary": true,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg"
			},
			"has_upcoming_events": true,
			"id": 16,
			"stats": {
				"event_count": 100
			},
			"score": 0.743116,
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"type": "mlb",
			"short_name": "Rangers",
			"home_venue_id": 16,
			"slug": "texas-rangers",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"home_team": true,
			"name": "Texas Rangers",
			"url": "https:\/\/seatgeek.com\/texas-rangers-tickets"
		}],
		"url": "https:\/\/seatgeek.com\/royals-at-rangers-tickets\/7-31-2016-arlington-texas-globe-life-park\/mlb\/2931970",
		"created_at": "2015-11-17T00:00:00",
		"venue": {
			"city": "Arlington",
			"name": "Globe Life Park",
			"extended_address": "Arlington, TX 76011",
			"url": "https:\/\/seatgeek.com\/venues\/globe-life-park\/tickets",
			"country": "US",
			"display_location": "Arlington, TX",
			"links": [],
			"slug": "globe-life-park",
			"state": "TX",
			"score": 0.861761,
			"postal_code": "76011",
			"location": {
				"lat": 32.7506,
				"lon": -97.0824
			},
			"address": "1000 Ballpark Way",
			"timezone": "America\/Chicago",
			"id": 16
		},
		"short_title": "Royals at Rangers",
		"datetime_utc": "2016-07-31T19:05:00",
		"datetime_tbd": false
	}, {
		"links": [],
		"id": 2931785,
		"stats": {
			"listing_count": 1968,
			"average_price": 49.0,
			"lowest_price_good_deals": 13.0,
			"lowest_price": 13.0,
			"highest_price": 410.0
		},
		"title": "Texas Rangers at Baltimore Orioles",
		"announce_date": "2015-11-17T00:00:00",
		"score": 0.741022,
		"date_tbd": false,
		"type": "mlb",
		"datetime_local": "2016-08-02T19:05:00",
		"visible_until_utc": "2016-08-03T03:05:00",
		"time_tbd": false,
		"taxonomies": [{
			"parent_id": null,
			"id": 1000000,
			"name": "sports"
		}, {
			"parent_id": 1000000,
			"id": 1010000,
			"name": "baseball"
		}, {
			"parent_id": 1010000,
			"id": 1010100,
			"name": "mlb"
		}],
		"performers": [{
			"away_team": true,
			"stats": {
				"event_count": 100
			},
			"name": "Texas Rangers",
			"short_name": "Rangers",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"url": "https:\/\/seatgeek.com\/texas-rangers-tickets",
			"type": "mlb",
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg",
			"home_venue_id": 16,
			"slug": "texas-rangers",
			"score": 0.743116,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg"
			},
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"has_upcoming_events": true,
			"id": 16
		}, {
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/baltimore-orioles-f8ad02\/25\/huge.jpg",
			"primary": true,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/baltimore-orioles-f8ad02\/25\/huge.jpg"
			},
			"has_upcoming_events": true,
			"id": 25,
			"stats": {
				"event_count": 101
			},
			"score": 0.690679,
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"type": "mlb",
			"short_name": "Orioles",
			"home_venue_id": 25,
			"slug": "baltimore-orioles",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League East",
				"short_name": "AL East",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-east"
			}],
			"home_team": true,
			"name": "Baltimore Orioles",
			"url": "https:\/\/seatgeek.com\/baltimore-orioles-tickets"
		}],
		"url": "https:\/\/seatgeek.com\/rangers-at-orioles-tickets\/8-2-2016-baltimore-maryland-oriole-park-at-camden-yards\/mlb\/2931785",
		"created_at": "2015-11-17T00:00:00",
		"venue": {
			"city": "Baltimore",
			"name": "Oriole Park at Camden Yards",
			"extended_address": "Baltimore, MD 21201",
			"url": "https:\/\/seatgeek.com\/venues\/oriole-park-at-camden-yards\/tickets",
			"country": "US",
			"display_location": "Baltimore, MD",
			"links": [],
			"slug": "oriole-park-at-camden-yards",
			"state": "MD",
			"score": 0.800769,
			"postal_code": "21201",
			"location": {
				"lat": 39.2839,
				"lon": -76.6223
			},
			"address": "333 West Camden St",
			"timezone": "America\/New_York",
			"id": 25
		},
		"short_title": "Rangers at Orioles",
		"datetime_utc": "2016-08-02T23:05:00",
		"datetime_tbd": false
	}, {
		"links": [],
		"id": 2932928,
		"stats": {
			"listing_count": 3536,
			"average_price": 71.5,
			"lowest_price_good_deals": 14.0,
			"lowest_price": 14.0,
			"highest_price": 1208.0
		},
		"title": "Texas Rangers at Houston Astros",
		"announce_date": "2015-11-17T00:00:00",
		"score": 0.775211,
		"date_tbd": false,
		"type": "mlb",
		"datetime_local": "2016-08-05T19:10:00",
		"visible_until_utc": "2016-08-06T04:10:00",
		"time_tbd": false,
		"taxonomies": [{
			"parent_id": null,
			"id": 1000000,
			"name": "sports"
		}, {
			"parent_id": 1000000,
			"id": 1010000,
			"name": "baseball"
		}, {
			"parent_id": 1010000,
			"id": 1010100,
			"name": "mlb"
		}],
		"performers": [{
			"away_team": true,
			"stats": {
				"event_count": 100
			},
			"name": "Texas Rangers",
			"short_name": "Rangers",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"url": "https:\/\/seatgeek.com\/texas-rangers-tickets",
			"type": "mlb",
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg",
			"home_venue_id": 16,
			"slug": "texas-rangers",
			"score": 0.743116,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/texas-rangers-a16a31\/16\/huge.jpg"
			},
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"has_upcoming_events": true,
			"id": 16
		}, {
			"image": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/houston-astros-da8e26\/20\/huge.jpg",
			"primary": true,
			"images": {
				"huge": "https:\/\/chairnerd.global.ssl.fastly.net\/images\/performers-landscape\/houston-astros-da8e26\/20\/huge.jpg"
			},
			"has_upcoming_events": true,
			"id": 20,
			"stats": {
				"event_count": 98
			},
			"score": 0.638755,
			"taxonomies": [{
				"parent_id": null,
				"id": 1000000,
				"name": "sports"
			}, {
				"parent_id": 1000000,
				"id": 1010000,
				"name": "baseball"
			}, {
				"parent_id": 1010000,
				"id": 1010100,
				"name": "mlb"
			}],
			"type": "mlb",
			"short_name": "Astros",
			"home_venue_id": 20,
			"slug": "houston-astros",
			"divisions": [{
				"display_name": "American League",
				"short_name": null,
				"division_level": 1,
				"display_type": "League",
				"taxonomy_id": 1010100,
				"slug": null
			}, {
				"display_name": "American League West",
				"short_name": "AL West",
				"division_level": 2,
				"display_type": "Division",
				"taxonomy_id": 1010100,
				"slug": "american-league-west"
			}],
			"home_team": true,
			"name": "Houston Astros",
			"url": "https:\/\/seatgeek.com\/houston-astros-tickets"
		}],
		"url": "https:\/\/seatgeek.com\/rangers-at-astros-tickets\/8-5-2016-houston-texas-minute-maid-park\/mlb\/2932928",
		"created_at": "2015-11-17T00:00:00",
		"venue": {
			"city": "Houston",
			"name": "Minute Maid Park",
			"extended_address": "Houston, TX 77002",
			"url": "https:\/\/seatgeek.com\/venues\/minute-maid-park\/tickets",
			"country": "US",
			"display_location": "Houston, TX",
			"links": [],
			"slug": "minute-maid-park",
			"state": "TX",
			"score": 0.74738,
			"postal_code": "77002",
			"location": {
				"lat": 29.7562,
				"lon": -95.3557
			},
			"address": "501 Crawford Street",
			"timezone": "America\/Chicago",
			"id": 20
		},
		"short_title": "Rangers at Astros",
		"datetime_utc": "2016-08-06T00:10:00",
		"datetime_tbd": false
	}]
}
```
