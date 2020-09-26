## Domain Name Suggestions

```javascript
/*
 * GET or POST to /v1/domain_suggestions
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

- responds with hundreds of alternative names, \
  paired with most relevant TLDs
- results which are most relevant and most likely to be available \
  are sorted to the top
- you choose which TLDs to promote (or demote)
- supports multiple TLDs as input, or category of TLDs
- special logic if the search term is a brand/name/tech/etc
- reliable word breaking (parse user input without spaces)

### API coming very soon to: [RapidAPI](https://rapidapi.com/besta-domains/api/domain-name-search1)

- Subscribe and send API requests immediately
- Test our data with no contract
- API documentation
- Code samples

### **Proof of concept demo: [Besta.Domains](https://besta.domains)**

- Use it to find an available domain name for your business
- See our data/algorithms in action, without getting technical

&nbsp;

### Request

- **GET** or **POST** to `http://api.besta.domains/v1/suggestions`.
- Pass data in the URL, or as POST data, or both. Example: we choose to send `?str=helloworld & tld=com` in URL, but all other options in POST data.
- If doing POST, use `content-type="application/json"`.

### Options

- "**tlds_num**" {number} - define how many TLD suggestions are returned, and used to make name suggestions. TLDs at the top of the list are most relevant, with the first one being the requested TLD. Besides the requested TLD, we also include "com" and "co". Then we include relevant TLDs which share the most meaning with the search term. Toward the bottom they get less relevant. So, you decide if you'd like more "quantity" or "quality".
- "**use_dashes**" {boolean} - default is "false", because people generally don't like dashes. If you pass "true", we'll use dashes, but sparingly, only for the most relevant results.
- "**use_spellcheck**" {boolean} - this runs your search term through Microsoft Bing Spellcheck before we start working on it. This request takes an extra 200-400 milliseconds. By turning this off, you can get the response faster. We still perform our own word-breaking and parsing. However, if the search term is misspelled, and this option is off, we may not be able to parse the input, and may not generate relevant results.
<!--However, our "broken" results are usually still better then others' "working" results. :)-->

### Future plans

We're working on adding options to let you:

- make the resulting names **shorter** (more catchy, but less likely to be available) or **longer** (more keywords, and more likely to be available)
- display all results as one flat list ("all"), instead of separated by type of suggestion ("name", "tld", "com", "word hack", "phrase hack")
- etc...
  We'll be adding documentation for each new feature as soon as it's ready.

All new features will be backwards compatible. To learn more about upcoming plans and integration options, [please contact us to schedule a demo](#contact).

&nbsp;
