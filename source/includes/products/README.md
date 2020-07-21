# Products  
  
We make business tools and linguistics APIs:  
  
* [**Best domain name suggestions**](https://rapidapi.com/nlp-studio/api/domain-name-search1) - most relevant, short, memorable, and available.  
* [**Most accurate synonyms**](https://rapidapi.com/nlp-studio/api/nlp-thesaurus1), parts of speech, word info, and sentiment analysis.  
  
We also make websites and apps:  
  
* [**nlp.domains**](https://nlp.domains) - Find an available domain name for your business  
* [**nlpthesaurus.com**](https://nlpthesaurus.com) - Thesaurus, word information, word sentiment  
* [**paulshorey.com**](https://paulshorey.com) - See other software made by Paul Shorey  
  
&nbsp;  
  
  
## Domain Name Suggestions and Availability  
```javascript  
/*  
 * GET /domain_suggestions?str=hello&tld=com  
 */  
{  
	"string": "hello world",  
	"string_original": "hellowrld",  
	"tld": "earth",  
	// the TLD suggestions, ordered by relevance  
	"tlds": [  
		"fyi", "info", "me", "us",  
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
  
/*  
 * GET /domain_availability?domains=["unavailable.co","premium.net","availableasffd.io"]  
 */  
{  
 "unavailable.co": 10,  
 "premium.net": 31459,  
 "availableasffd.io": 1  
}  
  
```  
* generate hundreds of alternative names and pairs them with relevant TLDs  
* many of the suggested domain names will be good and available!  
* besides full names, also returns just the suggested TLDs, in order of relevance  
* check the availability of 2000+ supported TLDs  
* check the expiration date for 1000+ supported TLDs  
* full WHOIS records - coming very soon  
  
### Get it on [RapidAPI](https://rapidapi.com/nlp-studio/api/domain-name-search1)  
  
* Subscribe and send API requests immediately (free trial)  
* Read documentation and code samples for every language  
* More in-depth documentation will be available here soon  
  
### **Try our app: [NLP.Domains](https://nlp.domains)**  
  
* Use it to find an available domain name for your business  
* See our data/algorithms in action, without getting technical  
  
  
<!-- Very soon, you'll be able to send API requests directly from your client front-end code, without worrying about exposing your secret headers. We're working on an optional parameter called `captcha_response` and `site_id`. You'll very soon be able to register your site with us, and configure your Captcha options, and many other site preferences. -->  
  
&nbsp;  
&nbsp;  
  
  
  
  
  
  
  
## NLP Thesaurus - Synonyms and Word info  
  
**Coming very soon** to RapidAPI  
  * synonyms grouped by part of speech, or as a flat list by relevance  
  * root, plural, singular, proper, conjunction, acronyms, abbreviations  
  * sentiment analysis \(positive or negative connotation\)  
  
**For now, please try our app: [NLPThesaurus.com](https://nlpthesaurus.com)**  
  
  
  
&nbsp;  
  
  
