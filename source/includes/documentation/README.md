# API Documentation

### Currently in beta testing, open to select registrars:

<b>Hostname: </b><a href="https://api.besta.domains" target="_blank">https://api.besta.domains</a>
<button class="subtle_button" onClick="window.location.href='#contactform'">Request API access</button>
<br />
<br />

### Domain Search:

[Suggestions](#domain-name-suggestions) - search a word, phrase, or domain - generate many alternative and available domain names, and most relevant TLDs \
[Availability - EPP/WHOIS based](#domain-name-availability) - check if domain is availabile or expiring soon (returns Unix timestamp of expiry date). \
[Availability - Nameserver based](#domain-name-availability) - check if domain is available or listed for sale. If Nameserver belongs to an aftermarket company like sedo.com or dan.com, it will be returned. This is the most reliable way to check if a domain is listed for sale somewhere. \
[Aftermarket price](#domain-name-availability) - search the domain name across all aftermarkets, return listing price and marketplace.

### Manage your TLDs:

[TLDs supported](#tlds-supported) - which TLDs you support, sort from most to least popular \
[TLDs promoted](#tlds-promoted) - which TLDs you own, and which you want to promote (or demote)\
[Default TLDs](#default-tlds) - when input is not a brand, name or tech

### Text Analysis:

[String breaking (chunking, parsing)](#string-breaking-chunking-parsing) - parse a long string of characters without spaces \
[Synonyms](#thesaurus) - synonyms for a word or short phrase - organized by part-of-speech\
[Word info](#word-info) - root word, plural or synonym derivation, abbreviation, acronym, syllable count, sentiment
