---
title: The Dice Jobs API Has Been Shut Down
date: 2017-10-28 21:13:55
tags:
- clients
- dice
---

Several years ago when I started the [JobAPIs project](https://github.com/jobapis), job boards were competing to get their jobs in front of as many people and developers as possible. Since then, there has been a lot of consolidation in the market (SimplyHired, another big player [shut down their whole site in 2016](https://techcrunch.com/2016/05/31/simply-hired-is-shutting-down-june-26-reportedly-as-part-of-an-acquisition/)), and some job boards have started holding their data more closely. With [Google entering the job aggregation space](http://www.onrec.com/news/news-archive/how-will-google-for-jobs-affect-traffic-for-the-major-job-sites), I think there's a lot of fear over where existing businesses will go in the next few years, but it seems that Dice has decided their business will go in a direction less friendly to developers.

As of October, 2017 the Dice Jobs API has been shut down. Dice has given me no reason for this, but there's nothing I can do about it. The [open source Dice Jobs library](https://github.com/jobapis/jobs-dice) we support no longer works, but I'm keeping it on Github and Packagist to prevent breaking anyone's dependencies. This is [the response I got from Dice](https://github.com/jobapis/jobs-dice/issues/8) when I asked about it:

```
Thank you for contacting us. Unfortunately Dice no longer has a public API. 

If you have any questions, or if I may be of any further assistance, please respond to this email or call me directly for faster resolution.

Thank you for choosing Dice and have a great day!
```

One user reported to me that he had a conversation with Dice about this, and he said that their API was never intended to be used by external developers anyway. Nevertheless, it was documented and at least [870 projects used](https://packagist.org/packages/jobapis/jobs-dice) the Dice job board adapter we released.
 
That's pretty much all I know about the shutdown at this point, but you're welcome to reach out if you have more information. To contact Dice, [you can fill out this form on their website](http://techhub.dice.com/Dice_General-ContactUs_D.html).
