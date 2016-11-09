---
title: Careerjet Jobs Provider Released
date: 2016-11-09 17:39:47
tags:
- releases 
- clients
- careerjet
---

Today we released the [first version of a Careerjet job board API client](https://github.com/jobapis/jobs-careerjet) using [Jobs Common v2](https://github.com/jobapis/jobs-common). Jobs Multi support will be released later this week as well.

To install the package, add it to your project's composer file:
 
```
composer require jobapis/jobs-careerjet
```

As with all [Jobs Common](https://github.com/jobapis/jobs-common) providers, you just need to create a Query:

```php
$query = new JobApis\Jobs\Client\Queries\CareerjetQuery([
    'keywords' => 'engineering',
    'location' => 'Chicago, IL',
    'page' => '1',
    'affid' => YOUR_AFFILIATE_ID,
]);
```

And inject it into the `CareerjetProvider`:

```php
$client = new JobApis\Jobs\Client\Provider\CareerjetProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-careerjet#usage), and as always, feel free to contact us if you'd like to get involved.

