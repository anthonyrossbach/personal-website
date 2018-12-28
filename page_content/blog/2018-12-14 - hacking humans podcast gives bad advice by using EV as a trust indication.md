## The last Hacking Humans podcast had Chris Bailey on who gave some really bad advice about using EV certificates!

I was walking downtown today and had the Hacking Humans podcast on that is hosted by Dave Bittner and Joe Carrigan and I was shocked by the segment with Chris Bailey. They told people (mainly Chris Bailey said) to use EV certificates as the indication of trust. This is really bad as EV has been shown to not be a trusted indicator at all and browsers like Chrome and Safari have removed the EV visuals so it wont show anymore. I am going to break this down and provide links to different sources.

You can find the transcript of the episode at https://thecyberwire.com/podcasts/cw-podcasts-hh-2018-12-13.html.

Also I started listening to the podcast because of the GOG podcast, that I found thanks to  thecyberwire, but I do NOT listen to thecyberwire anymore because of presentation and information being misleading.

----

### Lets start with EV is easy for a spammer to get if they want it
EV was seen as a way to validate who a company is, but they do not prove this as anyone with a company name can get one. Think of a company like Stripe, a USA based API for handling purchases and payments. Would you think that during a EV certificate getting created with the same name it would be denied? Well guess again as thats just what [Ian Carroll](https://twitter.com/iangcarroll) did. You can read more about that on https://stripe.ian.sh.

![](/images/blog/ian_firefox.png)

----

### EV certificates wont show on modern browsers
With the new version of iOS and macOS Safari removed the visual indicator for EV now only showing the domain and not showing the company name. Chrome is also testing and removing it also as they and many have found having EV does NOT give the users more trust.

Removal test as seen by [Troy Hunt](https://twitter.com/troyhunt) https://twitter.com/troyhunt/status/996259427962404864.

Troy Hunt's article: [Extended Validation Certificates are Dead](https://www.troyhunt.com/extended-validation-certificates-are-dead/).

----spotlight-start
![](/images/blog/chrome_evtest.jpg)
----spotlight-end

### Breaking down the points Chris Bailey made

> most people don't know about this. But many of the banks that you go to today - Bank of America or JPMorgan Chase or a U.S. bank, PayPal - when you go to those websites, they'll have a special indicator in the browser. And it's called an extended validation indicator.

The thing with this is that not only browsers are removing the indicators but also Paypal has not had a valid browser EV for months with it not showing the EV indicator for some browsers.

Just went to show PayPal as an example of a site using EV and saw... this. https://twitter.com/troyhunt/status/1042230559131426816
3 days later, PayPal still isn't showing the EV indicator in Chrome on Windows. Could it possibly be that it's just not that important? https://twitter.com/troyhunt/status/1043263452918108161

----

> will show you either the name of the organization and the country it's associated with or it'll actually show you that information in green. And that, actually, is also a really good indicator for the average person to look and see if they're actually at their real bank.

Hum, except if on Chrome for iOS or Android, Safari on macOS or iOS. Then I guess for mobile users they cant trust their bank as they just will NOT see this indication.

> That's correct. It's a difficult thing to spoof.

Not according to [Ian Carroll](https://twitter.com/iangcarroll) as per https://stripe.ian.sh with the best note: I spent less than an hour of my time and about $177. $100 of this was to incorporate the company, and $77 was for the certificate. It took about 48 hours from incorporation to the issuance of the certificate.

----

> And then the CA, the certification authority, really has only a few services offers after the fact. They actually will maintain that the certificate is still in good standing via revocation services, which are not commonly used, but we have to have that just in case it's needed.

Really? Hum... I guess it's not broken like almost all people in tech see it as.

[SSL certificate revocation and how it is broken in practice](https://medium.com/@alexeysamoshkin/how-ssl-certificate-revocation-is-broken-in-practice-af3b63b9cb3)

[Revocation is broken](https://scotthelme.co.uk/revocation-is-broken/)

[HTTPS Certificate Revocation is broken, and it’s time for some new tools](https://arstechnica.com/information-technology/2017/07/https-certificate-revocation-is-broken-and-its-time-for-some-new-tools/)

[Revocation doesn't work (18 Mar 2011)](https://www.imperialviolet.org/2011/03/18/revocation.html)

----

### The last point by Dave Bittner
> Obviously, for us, in the - you know, we figured in the business that we're in, it'd be good for us to have the most security we could have.

This is really harmful and makes people think that EV is more secure than a DV (Domain validated) certificate. This is entirely wrong and the security level of both is the exact same.

----

### Links to great articles
Look EV may work in time, but NOT for user trust but trust between systems in the back end. Users should not look for the EV indicators as they are being removed and don't actually give the users the info they need.

[Extended Validation Certificates are Dead](https://www.troyhunt.com/extended-validation-certificates-are-dead/) by [Troy Hunt](https://twitter.com/troyhunt).

[On The (Perceived) Value of EV Certs, Commercial CAs, Phishing and Let's Encrypt](https://www.troyhunt.com/on-the-perceived-value-ev-certs-cas-phishing-lets-encrypt/) by [Troy Hunt](https://twitter.com/troyhunt).

[Are EV certificates worth the paper they're written on?](https://scotthelme.co.uk/are-ev-certificates-worth-the-paper-theyre-written-on/) by [Scott Helme](https://twitter.com/Scott_Helme)

[FIRST PART OF PHISHING WITH EV](https://www.typewritten.net/writer/ev-phishing/)

[Phishing sites using Extended Validation SSL](https://news.netcraft.com/archives/2011/12/30/phishing-sites-using-extended-validation-ssl.html) from 2011.
