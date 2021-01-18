## TLDs Supported

`POST /v1/set_tlds_supported`

```javascript
/*
 * POST to /v1/set_tlds_supported:
 */
let postData = {
    site_id: "YOUR-SITE-ID",
    secret_key: "YOUR-PASSWORD",
    tlds: [
        "com", "net", "info", "us", "biz", "co",
        ...
        "online", "app", "website", "haus", "cat", "dog",
        ...
        "cyou", "ph", "jp", "gmbh"
    ]
}
/*
 * RESPONSE::
 */
{
    status: "success",
    message: "successfully updated your list of supported TLDs"
}
```

You tell us which TLDs to enable by sending us the full list of TLDs you support. Our [Domain Name Suggestions](#domain-name-suggestions) API will be limited to only these TLDs you have specified.

You arrange your list of TLDs from most desirable to least desirable. We'll sort our suggestions based on this order, and also by the scores you set in the [TLDs Promoted list](#tlds-promoted).

<!--To generate our name suggestions, we'll use this list. We'll include many names with TLDs from the front of the list. TLDs towards the back of the list will be included in our suggested names less frequently. Finally, with our [Domain Name Suggestions](#domain-name-suggestions) API, you may pass a variable "tlds_num", to specify how long this list should be. We'll cut off the list of suggested TLDs, and ignore the excess.-->

**This step is optional.** If you skip it, we'll just return ALL relevant TLDs. You can then filter out ones you don't support on your own end.

### Request

**POST** to `/v1/set_tlds_supported`, a JSON array of tlds.

&nbsp; \
**More info [coming soon](javascript:document.querySelector('.eapps-form-floating-button').click())**. This is not yet available. \
&nbsp;

## TLDs Promoted

`POST /v1/set_tlds_promoted`

```javascript
/*
 * POST to /v1/set_tlds_promoted:
 */
let postData = {
    site_id: "YOUR-SITE-ID",
    secret_key: "YOUR-PASSWORD",
    tlds: {
        design: 500,
        wiki: 100,
        ink: 75,
        gay: 50,
        ...
        store: 5,
        ai: 5,
        org: 5,
        app: 5,
        fun: 4,
        ...
        computer: -4,
        edu: -4,
        tel: -5,
        diet: -5,
        army: -10,
        airforce: -10,
    }
}

/*
 * RESPONSE::
 */
{
    status: "success",
    message: "successfully updated your list of promoted TLDs"
}
```

**This step is optional.** Specify which TLDs you wish to promote or demote. Specify how aggressively you'd like to promote each TLD by giving each a score.

We will use the values in this list to sort our list of TLD suggestions. TLDs with a higher score will be sorted towards the top of the list, and used more frequently. Low scores will be sorted towards the end of the list, and used less frequently.

**Example: the company TopLevel.Design would promote "wiki, ink, design, and gay" by giving each tld a rating of 10 or higher.** Thus, whenever these are even slightly relevant to the user's search term, they will be used and promoted towards the top of the list. They will be promoted intelligently, by relevance, not necessarily to the very top, but sometimes to the middle of the list if they're not very relevant to the search term. To always promote to the very top, whenever slightly relevant, set an super high value like 10000.

Ignore the values in the code example. We already correct for words that appear too often or not enough. **Just set a high or low number based on how much YOU want to promote or demote each TLD.** Zero (0) is neutral and is the default value. 5 will promote a TLD approximately 5 positions higher than one rated 0. 10 will promote 10 places higher/lower, etc. It's not exactly one for one, but this is a good starting point. Feel free to be more agressive and use an extreme value like +-1000 when you want something to go all the way to the top or all the way to the bottom.

### Request

**POST** to `/v1/set_tlds_promoted`, an object of key/value pairs, where the key is the TLD (without the leading dot), and the value is the rating you want to give it (usually < 10 to promote and > -10 to demote). Zero (0) has no effect. So, don't bother setting values for TLDs you neither wish to promote or demote.

&nbsp; \
**More info [coming soon](javascript:document.querySelector('.eapps-form-floating-button').click())**. This is not yet available. \
&nbsp;

## Default TLDs

`POST /v1/set_tlds_default`

```javascript
/*
 * POST to /v1/set_tlds_default:
 */
let postData = {
    site_id: "YOUR-SITE-ID",
    secret_key: "YOUR-PASSWORD",
    tech: [
      "app", "dev", "ai", "wiki", "io", "co", ...
    ],
    name: [
      "me", "moi", "name", "works", "studio", ...
    ],
    brand: [
      "online", "solutions", "llc", "best", "co", ...
    ],
    default: [
      "com", "co", "net", "us", "biz", "info", ...
    ]
}

/*
 * RESPONSE::
 */
{
    status: "success",
    message: "successfully updated your default TLDs"
}
```

Specify which TLDs you'd like to use by default, if the search term was too obscure to match any synonym-based results.

We detect if the user's search term mentions a category. Our list of categories is growing, and will be updated here in the future. This feature is still being developed, but is already very useful - better than not having it. You can specify the default list of TLDs to use for each category of keyword - "tech term", "brand name", "person's name", "food", or "a place or destination".

This is also useful if our system comes up with very few TLDs. Then, we'll use the relevant TLDs we found first. Then, we'll mix in these default values to finish the list. We have to use something, because if we generate phrases, we'll have to pair them with TLDs. Can't just rely on ".com"s anymore.

**This is optional.** We have our own lists of default TLDs. If you skip this part, we'll use our own lists. You only have to set [which TLDs you support](#tlds-supported). We'll ignore the ones you don't support.

### Request

**POST** to `/v1/set_tlds_default`, lists of tlds, by category. See code example.

&nbsp; \
**More info [coming soon](javascript:document.querySelector('.eapps-form-floating-button').click())**. This is not yet available. \
&nbsp;
