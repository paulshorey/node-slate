## TLDs Supported

Specify which TLDs you support. Then, our [Domain Name Suggestions](#domain-name-suggestions) API will be limited to only these TLDs. It will never return TLDs which are NOT on this list.

Sort these TLDs from most desirable (com, co, io, site, app) to least desirable (gmbh, ph, net.vc, jp.net). We'll use the sort order of this list to sort our list of TLD suggestions. We will also use the [TLDs Promoted](#tlds-promoted) list, which you should also set.

We support all possible TLDs, btw. This is just to limit our TLDs to ones which are useful to your implementation.

More info [coming soon](#contact).

## TLDs Promoted

```
  store: 5,
  design: 5,
  ai: 5,
  org: 5,
  app: 5,
  fun: 4, // it's fun!
  studio: 1,
  games: 1,
  movie: 1,
  film: 1,
  dev: 0,
  tech: -1,
  singles: -1,
  work: -1, // don't like to work :)
  parts: -2, // because it's kind of negative, like "junkyard", "for repair", "not working"
  graphics: -2, // occurs too frequently, too long
  lgbt: -2,
  domains: -5, // very narrow use case
  red: -2,
  navy: -2,
  green: -2,
  wtf: -3, // crude
  porn: -3, // naughty!
  ngo: -4, // comes up often in synonyms... but does anybody actually want this TLD?
  museum: -10, // big lengthy process to apply and be accepted, but a great TLD!
  new: -10, // application process and strict requirements
  aero: -10,
  bot: -10,
  onl: -5, // usually un-registered, so comes up in results too much
  edu: -5,
  tel: -5,
  diet: -5, // comes up too much as a synonym, not the most useful tld
  computer: -3, // too long
  army: -10, // too violent
  airforce: -10
```

Specify which TLDs you wish to support, promote, or demote. Specify how aggressively you'd like to promote each TLD by giving each a score.

We will use the values in this list to sort our list of TLD suggestions. TLDs with a higher score will be sorted towards the top of the list, and used more frequently. Low scores will be sorted towards the end of the list, and used less frequently.

You will be able to modify this list (and any other setting) as often as you like, using our admin tool (coming soon) or API. Then, you'll be able to test in real time, how the suggestions look. It may take a bit of trial and error to get your results to be perfect... However, it doesn't have to be hard...

Just take our list, shown here. Add to the top of it all the TLDs you own, each with a rating of '10'. This way, you keep the settings we developed, but promote your favorite TLDs. **For example, the company TopLevel.Design** would add "wiki, ink, design, and gay" to the list, each with a value of 10.

More info [coming soon](#contact).

## Default TLDs

Specify which TLDs you'd like to add if the user's search term was too obscure, and did not yield any synonym-based or category-based related TLDs.

More info [coming soon](#contact).

## Default Brand TLDs

Specify which TLDs you'd like to add if the user's search term mentioned a brand name, or what we detect is not a dictionary word, but probably a brand name.

More info [coming soon](#contact).

## Default Name TLDs

Specify which TLDs you'd like to add if the user's search term mentioned a person's name.

More info [coming soon](#contact).

## Default Tech TLDs

Specify which TLDs you'd like to add when the user's search term mentioned a technology term.

More info [coming soon](#contact).
