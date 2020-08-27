## Domain Name Suggestions

```javascript
{
    // GET /domain_suggestions?str=hellowrld&tld=com
	"string_original": "hellowrld",
	"tld": "com",
    // spell-checked, chunked input
	"string": "hello world",
	// suggested TLDs, ordered by relevance
	"tlds": [
		"world", "fyi", "earth", "info", "global", "me", "international", "us", "eco",
	],
    // suggested names, grouped by type of modification
	"domains": {
		"tld": [
			"hellowrld .fyi",
			"hellowrld .earth",
			"hellowrld .info",
			"hellowrld .global"
		],
		"name": [
			"hola society .com",
			"howdy .earth",
			"well hello .world",
			"shalom .travel",
			"earth .eco",
			"hello there .earth",
			"society .space",
		],
		"hack": [
			"worlda .eco",
			"planet .io",
			"orbus .org",
		]
	}
}

```

**Proof of concept version (alpha release) now available!**

- generate hundreds of alternative names, \
  paired with most relevant TLDs
- results which are most relevant and most likely to be available \
  are sorted to the top
- you choose which TLDs to promote (or demote)
- supports multiple TLDs as input, or category of TLDs
- special logic if the search term is a brand/name/tech/etc
- reliable word breaking (parse user input without spaces)

### API available at [RapidAPI](https://rapidapi.com/nlp-studio/api/domain-name-search1)

- Subscribe and send API requests immediately (free trial)
- API documentation
- Code samples

### **Demo app: [NLP.Domains](https://nlp.domains)**

- Use it to find an available domain name for your business
- See our data/algorithms in action, without getting technical

&nbsp;

See [documentation](#documentation) for more customizations and sorting options. We'll add documentation for each feature as soon as it's ready. All features will be backwards compatible. Please [contact us to schedule a demo](#contact), to learn about all upcoming features and integration options.

&nbsp;
