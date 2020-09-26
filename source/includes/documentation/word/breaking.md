## Parse domain name string (string breaking, word chunking)

When searching for a domain name, or anything - if your user inputs a string of characters with no spaces - most software is not able to make sense of it.

**Break the string of characters into individual words**, with **info about each word** - part of speech, root, singular/plural, **and sentiment analysis**.

By default, this uses help from Microsoft Bing Spellcheck. You can turn off this functionality to get your response a few hundred milliseconds faster. However, then our parsing may not work well if the search term contains a typo.

&nbsp; \
**Demo: [besta.domains](https://besta.domains)** Enter a long domain name with no spaces. We'll parse it into individual words, then suggest TLDs, synonyms, and word hacks based on those words. Click "thesaurus" link on the right (on desktop only). It will expand to let you see "behind the scenes", what words we parsed. \
**More info [coming soon](#contact)** \
&nbsp;
