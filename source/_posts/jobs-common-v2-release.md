---
title: Jobs Common Version 2 Release
date: 2016-09-03
author: Karl Hughes
tags:
- releases
- jobs-common
---

For the past year or so I've been meaning to invest the time in a version 2 of the [Jobs Common](https://github.com/jobapis/jobs-common) package, and I finally got around to releasing it this morning.

## What's new in version 2?
Most of the improvements are internal. My goal was to make creating a new provider faster and easier while allowing maximum flexibility for unique parameters or response objects. Basically, this means that it's now easier to create a new client with Jobs Common.

- **New AbstractQuery object** - In version 1, attributes were set directly on the Provider class (eg: `$provider->setKeyword('engineer');`. In version 2, you set attributes on a new Query class and then inject that into the Provider. The AbstractQuery handles most of the heavy lifting; you just have to add all the attributes from the API and fill in a couple abstract methods.
- **AbstractProvider handles parsing responses** - With the new AbstractQuery, the Provider is now primarily responsible for handling the response from the API. It basically checks that the Query is valid and uses it to make a call (still using Guzzle), then parses the response. As such, the abstract method signatures have changed here.
- **Concrete classes in a "/fixtures" folder for testing** - Another improvement in version 2 is the inclusion of two Concrete classes intended to demonstrate creating a new Client and improve testability of the abstract classes.

## Which providers are using version 2?
Currently we have updated the most popular providers to use jobs-common version 2:

- [Indeed](/open-source/indeed/)
- [Government Jobs](/open-source/govt/)
- [Dice](/open-source/dice/)
- [Careerbuilder](/open-source/careerbuilder/)

My plan is to release a new provider every 1-2 weeks until I've got them all running on v2.

## Other announcements

#### SimplyHired API indefinitely shut down
[SimplyHired was sold this summer](https://techcrunch.com/2016/05/31/simply-hired-is-shutting-down-june-26-reportedly-as-part-of-an-acquisition/), and it looks like they've [shut off their API indefinitely](http://www.simplyhired.com/about/publishers). Until I hear that it's back up, I'm discontinuing support for the [SimplyHired jobs provider](https://github.com/jobapis/jobs-simplyhired).

#### Jobs Multi coming up
Finally, the next project in the jobs space that I'll be tackling is an effort at standardizing the input parameters for job board APIs.

While Jobs Common standardizes the output of job boards using the [schema.org JobPosting standard](https://schema.org/JobPosting) it makes no attempt at standardizing the input parameters used for each provider. This is intentional. When I first started the project, I tried to do this, but as I've used Jobs Common for a couple different use cases now, I've realized that it was not appropriate.

So, the Jobs Common package and each Provider will remain useful as independent packages, and Jobs Multi will make it easy to access each job board using standard language.

I don't have many specifics yet as I'm just starting to plan for this, but my guess will be that the external API will allow for things like:

```php

$allJobs = new Multi();

$providers = [
    'Indeed',
    'Dice',
    'Careerbuilder',
];

$results = $allJobs->setKeyword('sales')
    ->setLocation('Memphis, TN')
    ->setProviders()
    ->perPage('100');

```

Because the goal will be to standardize inputs that aren't always equivalent, there will be some opining in this package that may or may not be appreciated by users. I get it, and I'd welcome contributions or alternative solutions to this problem.

That's all for this week. Looking forward to getting more quality open source jobs software out soon!
