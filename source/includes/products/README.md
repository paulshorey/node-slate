# Products & Documentation  
  
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
  
- generate hundreds of alternative names and pairs them with relevant TLDs  
- many of the suggested domain names will be good and available!  
- besides full names, also returns just the suggested TLDs, in order of relevance  
- check the availability of 2000+ supported TLDs  
- check the expiration date for 1000+ supported TLDs  
- full WHOIS records - coming very soon  
  
### Get it on [RapidAPI](https://rapidapi.com/nlp-studio/api/domain-name-search1)  
  
- Subscribe and send API requests immediately (free trial)  
- Read documentation and code samples for every language  
- More in-depth documentation will be available here soon  
  
### **Try our app: [NLP.Domains](https://nlp.domains)**  
  
- Use it to find an available domain name for your business  
- See our data/algorithms in action, without getting technical  
  
&nbsp;  
  
More in-depth documentation coming soon.  
  
&nbsp;  
  
## NLP Thesaurus - Synonyms and Word info  
  
**Coming very soon** to RapidAPI  
  
- synonyms grouped by part of speech, or as a flat list by relevance  
- root, plural, singular, proper, conjunction, acronyms, abbreviations  
- sentiment analysis \(positive or negative connotation\)  
  
**For now, please try our app: [NLPThesaurus.com](https://nlpthesaurus.com)**  
  
&nbsp;  
