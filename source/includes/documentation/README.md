# Documentation  
  
## Domain Name Suggestions API  
```javascript  
{  
  // your input string, spell-checked and chunked  
	"string": "hello world",  
	"string_original": "hellowrld",  
	// if you did not input a TLD, we'll use "com"  
	"tld": "earth",  
	// the TLD suggestions, ordered by relevance  
	"tlds": [  
		"fyi",  
		"info"  
	]  
  // the name suggestions, grouped into categories  
	"domains": {  
		"tld suggestions": [  
			"hellowrld .fyi",  
			"hellowrld .world"  
		],  
		"name suggestions": [  
			"hello world .eco",  
			"hello earth .news"  
		],  
		"word hacks": [  
			"shalomio .com",  
			"wassupo .com"  
		]  
	},  
	"error_message": "",  
}  
```  
**GET** [/mvp/domain_suggestions?str=hello&tld=com](https://domain-name-search1.p.rapidapi.com/mvp/domain_suggestions?str=hello&tld=com) ⇨  
  
**[Available on RapidAPI](https://rapidapi.com/nlp-studio/api/domain-name-search1)**  
  
You can now sign up for a free trial and send API requests immediately from their site. They even have code examples in every language and framework, to help you integrate.  
  
Very soon, you'll be able to send API requests directly from your client front-end code, without worrying about exposing your secret headers. We're working on an optional parameter called `captcha_response` and `site_id`. You'll very soon be able to register your site with us, and configure your Captcha options, and many other site preferences.  
  
More in-depth documentation coming soon.  
  
  
## Domain Name availability and expiration  
```json  
{  
 "unavailable.co": 10,  
 "premium.net": 31459,  
 "availableasffd.io": 1  
}  
```  
**GET** [/mvp/domain_availability?domains=["unavailable.co","premium.net","availableasffd.io"]](https://domain-name-search1.p.rapidapi.com/mvp/domain_availability) ⇨  
  
**[Available on RapidAPI](https://rapidapi.com/nlp-studio/api/domain-name-search1)**  
  
You can now sign up for a free trial and send API requests immediately from their site. They even have code examples in every language and framework, to help you integrate.  
  
Very soon, you'll be able to send API requests directly from your client front-end code, without worrying about exposing your secret headers. We're working on an optional parameter called `captcha_response` and `site_id`. You'll very soon be able to register your site with us, and configure your Captcha options, and many other site preferences.  
  
In-depth documentation coming soon.  
  
  
&nbsp;