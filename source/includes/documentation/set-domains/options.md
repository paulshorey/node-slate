## TLDs Supported

```javascript
/*
 * POST to /v1/tlds_supported (JSON format)
 */
let requestData = {
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
 * OUTPUT (JSON format):
 */
{
    status: "success",
    message: "successfully updated your list of supported TLDs"
}
```

You tell us which TLDs to enable. Our [Domain Name Suggestions](#domain-name-suggestions) API will be limited to only these TLDs that you specified. It will never return TLDs which are NOT on this list.

You arrange all supported TLDs from most desirable to least desirable. We'll sort our suggestions based on this order, multiplied by the score in the [TLDs Promoted](#tlds-promoted) list. Then, we will return to you the sorted list, and use it to make our name suggestions.

<!--To generate our name suggestions, we'll use this list. We'll include many names with TLDs from the front of the list. TLDs towards the back of the list will be included in our suggested names less frequently. Finally, with our [Domain Name Suggestions](#domain-name-suggestions) API, you may pass a variable "tlds_num", to specify how long this list should be. We'll cut off the list of suggested TLDs, and ignore the excess.-->

### Request

**POST** to `/v1/tlds_supported`, a JSON array of tlds.

&nbsp; \
**More info [coming soon](#contact)** \
&nbsp;

## TLDs Promoted

```javascript
/*
 * POST to /v1/tlds_promoted (JSON format)
 */
let requestData = {
    site_id: "YOUR-SITE-ID",
    secret_key: "YOUR-PASSWORD",
    tlds: {
        store: 5,
        design: 5,
        ai: 5,
        org: 5,
        app: 5,
        fun: 4,
        ...
        computer: -3,
        edu: -4,
        tel: -5,
        diet: -5,
        army: -10,
        airforce: -10,
    }
}

/*
 * OUTPUT (JSON format):
 */
{
    status: "success",
    message: "successfully updated your list of promoted TLDs"
}
```

Specify which TLDs you wish to support, promote, or demote. Specify how aggressively you'd like to promote each TLD by giving each a score.

We will use the values in this list to sort our list of TLD suggestions. TLDs with a higher score will be sorted towards the top of the list, and used more frequently. Low scores will be sorted towards the end of the list, and used less frequently.

**Example, the company TopLevel.Design would promote "wiki, ink, design, and gay"** by giving each tld a rating of 10 or higher. Thus, whenever these are even slightly relevant to the user's search term, they will be used and promoted towards the top of the list. They will be promoted intelligently, by relevance, not necessarily to the very top, but often to the middle of the list. To always promote to the very top, whenever slightly relevant, set an unreasonably high value of 10000.

**This is optional** This is only to promote TLDs for reasons other than relevance.

We have our own list of TLD ratings. The values in the example code are from our list. The purpose of our own ratings is to account for biases in our synonym-based suggestion model, to make sure some TLDs do not always come up more than others. For example, "airforce" comes up a lot for anything about airplanes or flying. However, most people looking for a domain do not want such a specific TLD. They're probably just looking for "travel". So, we've agressively lowered its importance.

We'll add your ratings to ours. So, ignore the values in the code example. Just set a high or low number based on how much YOU want to promote or demote each TLD. Zero (0) is neutral and is the default value. 5 will promote a TLD approximately 5 positions higher than one rated 0. 10 will promote 10 places higher/lower, etc. It's not exactly one for one, but this is a good starting point.

### Request

**POST** to `/v1/tlds_promoted`, an object of key/value pairs, where the key is the TLD, without the leading dot, and the value is the rating you want to give it, usually upto 10 to promote, and upto negative -10 to demote. Zero (0) has no effect. So, you don't need to set a value for ALL TLDs, just the ones that are not zero.

&nbsp; \
**More info [coming soon](#contact)** \
&nbsp;

## Default TLDs

```javascript
/*
 * POST to /v1/tlds_default (JSON format)
 */
let requestData = {
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
 * OUTPUT (JSON format):
 */
{
    status: "success",
    message: "successfully updated your default TLDs"
}
```

Specify which TLDs you'd like to use by default, if the search term was too obscure to match any synonym-based results.

We detect if the user's search term mentions a category. Our list of categories is growing, and will be updated here in the future. This feature is still being developed, but is already very useful - better than not having it. You can specify the default list of TLDs to use if the user typed in a "tech term", "brand name", "person's name", "food", or "a place or destination".

**This is optional** We have our own lists of default TLDs. See below. You only have to set [which TLDs you support](#tlds-supported). We'll ignore the ones you don't support.

**Tech** - [see our default list of TLDs to pair with a tech term](https://docs.besta.domains/files/domains/example-tlds-default-tech) \
**Brand** - [see our default list of TLDs to pair with a brand name](https://docs.besta.domains/files/domains/example-tlds-default-tech) \
**Name** - [see our default list of TLDs to use if the person searched a name](https://docs.besta.domains/files/domains/example-tlds-default-tech) \
**Default** - [see our default list of TLDs to use if we could not find any relevant suggestions](https://docs.besta.domains/files/domains/example-tlds-default-tech)

### Request

**POST** to `/v1/tlds_default`, lists of tlds, by category, see code example.

&nbsp; \
**More info [coming soon](#contact)** \
&nbsp;
