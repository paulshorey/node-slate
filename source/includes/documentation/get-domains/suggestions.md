# Domain Suggestions

`POST /v1/domain_suggestions` &nbsp;<span style="position:relative;top:-1.22rem;"><a href="/openAPI/v1-domain-suggestions.yaml" download>OpenAPI <sub><img class="side-contact-icon" alt="download openAPI file" src="/images/openAPI/file-download.svg" /></sub></a> </span>

```javascript
/*
 * GET or POST to /v1/suggestions
 */
let requestData = {
  str: 'helloworld', // required
  tld: 'com', // optional,
  use_word_hacks: true, // optional, boolean
  use_phrase_hacks: true, // optional, boolean
  use_spellcheck: true, // optional, boolean
  use_dashes: false, // optional, boolean
  use_before: true, // optional, boolean
  tlds_num: 30, // optional, number
}

/*
 * OUTPUT (JSON format):
 */
{
    "string_original": "hellowrld",
    "tld": "com",
    // spell-checked, chunked input
    "string": "hello world",
    // suggested TLDs, ordered by relevance
    "tlds": [
        "world", "fyi", "earth", "info", "global", "travel", "international", "us", "eco"
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
            "society .space"
        ],
        "word hack": [
            "worlda .eco",
            "planet .io",
            "orbus .org"
        ],
        "phrase hack": [
            "get hellowrld .eco",
            "my hellowrld .app",
            "hellowrld online .com"
        ],
        "all": [
            "hellowrld .fyi",
            "hola society .com",
            "worlda .eco",
            "get hellowrld .eco",
            "hellowrld .earth",
            "howdy .earth",
            "planet .io",
            "my hellowrld .app",
        ]
    }
}

```

- get hundreds of domain name suggestions
- paired with the most relevant TLDs
- sort by relevance, length, or by likelihood of availability
- you can [choose which TLDs to promote](#tlds-promoted) (or demote)
- supports multiple TLDs as input, or category of TLDs
- special logic if the search term is a brand/name/tech/etc
- reliable word breaking (parse user input without spaces)

### [Get it at RapidAPI<span class="icon-external-link"></span>](https://rapidapi.com/besta-domains/api/domain-suggestions-tlds)

- Subscribe and send API requests immediately
- Test our data with no contract
- API documentation and code samples

### [Demo at Besta.Domains<span class="icon-external-link"></span>](https://besta.domains)

- Use it to find an available domain name for your business
- See our data/algorithms in action, without getting technical

### Request:

**POST** data to `http://api.besta.domains/v1/suggestions`, using `content-type="application/json"`.\
You may also send variables as "URL Query parameters". \
 Example: We choose to send "str" and "tld" in the URL (`POST TO /v1/suggestions?str=helloworld&tld=com`), and all other options as POST data.

### POST data or URL params:

- **str** {string} - is the only required variable. It is the search keyword or phrase (ex: "fun times" or "funtimes"), or the domain you wish to buy (ex: "funtimes.com"). If your user inputs the phrase with spaces, please **keep the spaces whenever possible**. If the string does not have spaces, we will attempt to parse individual words from it (ex: input "unitedstates", we'll parse it as "united" and "states" and "united states").

- **tld** {string} - (optional, default="com") may be passed as a separate variable here, or as part of the **str**. Complex and non-English TLDs like ".co.uk" and ".购物" are allowed, and will work fine, but we do not yet parse added meaning from them. However, if the TLD is an English word like ".travel", we will parse meaning from it, and suggest similar words and TLDs.

**Note:** if the **str** ends with a TLD, like "goodnews.app", then this TLD, parsed from **str** will be used, even if you specified a **tld** value. So, you do not have to worry about parsing the tld on your end. We will do it for you.

- **tlds_num** {number} - (optional, default=30) define how many TLD suggestions are returned, and used to make name suggestions. TLDs at the top of the list are most relevant. Toward the bottom they get less relevant. So, you decide if you'd like more "quantity" or "quality". This list of TLDs is also used by our script to generate the domain names. So, if you specify a low number, we'll only use the most relevant few TLDs in the suggestions results. Or you may choose a higher number to feature a greater variety of TLDs.

### Response:

See code example to the top/right. It is a shortened example of response data for input `?str=helloworld&tld=com` or `?str=helloworld.com`. The suggestions are grouped by category inside response `data.domains`. You may mix together the categories yourself, or use our aggregated `data.domains.all` list. To get simply a list of suggested TLDs, use `data.tlds`.

### More options coming soon:

- make the suggested names **shorter** (more catchy, but less likely to be available) or **longer** (more keywords, and more likely to be available)
- combine all suggestions into one list. Currently, it is sent as separate lists, grouped by type of manipulation ("name", "tld", "com", "word hack", "phrase hack")
- enable or disable the "word hacks", "phrase hacks", "domain hacks", or "com" suggestions (currently, you can just ignore a section if you don't like it)

&nbsp;

All new features will be backwards compatible. [Contact us](<javascript:document.querySelector('.eapps-form-floating-button').click()>) to learn about upcoming features, and to suggest some that are important to you.
