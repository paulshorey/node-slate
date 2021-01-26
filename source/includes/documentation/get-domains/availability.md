# Domain Availability

`POST /v1/domain_availability` &nbsp;<span style="position:relative;top:-1.22rem;"><a href="/openAPI/v1-domain-availability.yaml" download>OpenAPI <sub><img class="side-contact-icon" alt="download openAPI file" src="/images/openAPI/file-download.svg" /></sub></a> </span>

```javascript
/*
 * Status code legend:
    -1 = unknown, not able to check
    0 = new, did not check
    1 = unavailable
    2 = available
    3 = registry premium (buy it now for higher price than such TLD normally sells for)
    4 = aftermarket premium (buy it now or make an offer, also could be in an auction)
    5 = registry super-premium (must submit offer, more expensive than regular premium SLDs)
    6 = unavailable, but expiring soon
 */

/*
 * POST to /v1/availability:
 */
let postData = {
  "method": "domainr",
  "domains": [
    "premium.net",
    "besta.domains",
    "greata.domains",
    "perfect.domains",
    "true.domains",
    "best.domains",
    "new.domains"
  ]
}

/*
 * RESPONSE DATA (use Domainr.com API)
 * We have engineered an abstration layer on top of Domainr.com.
 * Our server checks many domains in parallel, instead of
 * one by one. So, get results upto 100 times faster!
 */
{
  "method": "domainr",
  "status": {
    "premium.net": 4, // aftermarket
    "besta.domains": 1, // not available
    "greata.domains" 2, // available
    "perfect.domains": 3, // registry premium
    "true.domains": 4, // aftermarket
    "best.domains": 1, // not available
    "new.domains": 5 // registry super-premium
  }
}

/*
 * RESPONSE DATA (use whois/nameservers) (COMING SOON)
 * This will be able to find which aftermarket service the
 * domain is listed in. Also, most reliable at telling if the
 * domain is listed in an aftermarket. Also, it can tell if
 * a domain name is expiring soon, and return the expiry date.
 * Unfortunately, it can NOT reliably tell if a domain is
 * simply "available to register".
 */
{
  "method": "whois/nameservers",
  "status": {
    "premium.net": 4, // aftermarket
    "besta.domains": 1, // not available
    "greata.domains" -1, // unknown
    "perfect.domains": 3, // registry premium
    "true.domains": 4, // aftermarket
    "best.domains": 4, // aftermarket
    "new.domains": 5 // registry super-premium
  },
  "aftermarket": {
    "premium.net": "sedo.com",
    "true.domains": "auctions.godaddy.com",
    "best.domains": "dan.com",
    "new.domains": "name.com",
  }
  "expiration": {
    // if a domain is expiring soon, it will be
    // included here just like data.aftermarket
  }
}
```

- check all valid TLDs (generic, new, cc, etc)
- check if a domain is available, unavailable, premium (set by registry), or premium (listed in aftermarket)
- **check 100 domains at a time**, or upto 500 with contract

### [Get it at RapidAPI<span class="icon-external-link"></span>](https://rapidapi.com/besta-domains/api/domain-availability-bulk)

- Subscribe and send API requests immediately
- Test our data with no contract
- API documentation and code samples

### [Demo at Besta.Domains<span class="icon-external-link"></span>](https://besta.domains)

- Use it to find an available domain name for your business
- See our data/algorithms in action, without getting technical

### Request:

**POST** to `http://api.besta.domains/v1/availability`, using `content-type="application/json"`.

### Send Data:

- "**method**" {string} - Which method to use, to check availability. Default value is "domainr". Other options are experimental.
- "**domains**" {array} - It should be an array of domain names. Up to 100 items at a time, or upto 500 with contract.
- "**show_metadata**" {boolean} - Default is "false". If "true", will show information about each status, if available. If using Domainr API, will include a "domainr" dictionary, with their "status" message for each of the requested domains. When using WHOIS/NameServer option (coming soon), will show nameserver, aftermarket, and expiration dates when available.

### Response:

See code sample above/right for an example response. You send an array of domains. We return the same domains, in an object. Value = status code.

**Value for each domain is one of these codes:** \
**-1**: **unknown**, not able to check\
**0**: **new**, did not check\
**1**: **unavailable**\
**2**: **available**\
**3**: **registry** premium (buy it now for higher price than such TLD normally sells for)\
**4**: **aftermarket** premium (buy it now or make an offer, also could be in an auction)\
**5**: **registry** premium marketed (must submit offer, more expensive than regular premium SLDs)\
**6**: **unavailable**, but expiring soon (includes expiration date - check data.expiration)

-1: unknown, not able to check
0: new, did not check
1: unavailable
2: available
3: registry premium (buy it now for higher price than such TLD normally sells for)
4: aftermarket premium (buy it now or make an offer, also could be in an auction)
5: registry premium marketed (must submit offer, more expensive than regular premium SLDs)
6: unavailable, but expiring soon (includes expiration date - check data.expiration)

### More options coming soon:

Specify the "method", which strategy to use, to check availability:

1. "domainr" - (default) Domainr.com API. Fastest. We have engineered an abstration layer on top of the excellent Domainr.com API. Our server checks many domains in parallel, instead of one by one. So, you get results upto 100 times faster!
2. "whois/nameservers" - (in development, not ready) Fast. Most reliable at telling if the domain is listed in an aftermarket. It can actually tell you which aftermarket! For most domains it can check if expiring soon and return the date of expiration. Unfortunately, it can NOT reliably tell if a domain is simply "available to register". So, it must be used in conjunction with another method.
3. "registry/epp" - (coming in the future) Slower. Currently getting accredited and registered with various registries. This is coming soon. We'll be able to use the same tools which registrars use.
