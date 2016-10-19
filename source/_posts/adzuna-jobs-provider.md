---
title: Adzuna Job Board Api Client Released
date: 2016-10-18 21:13:55
tags:
- releases 
- clients
- careercast
---

Our latest PHP job board client is for [Adzuna](https://github.com/jobapis/jobs-adzuna) a largely European job board with a private API for registered partners. You can [register to use Adzuna's API here](https://developer.adzuna.com/admin), and get started using this API client by including the package in your project's composer file:
 
```
composer require jobapis/jobs-adzuna
```

As with all [Jobs Common](https://github.com/jobapis/jobs-common) providers, you just need to create a Query:

```php
$query = new JobApis\Jobs\Client\Queries\AdzunaQuery([
    'what' => 'engineering',
    'where' => 'London, UK',
    'page' => '1',
    'app_id' => YOUR_APP_ID,
    'app_key' => YOUR_APP_KEY,
]);
```

And inject it into the `AdzunaProvider`:

```php
$client = new JobApis\Jobs\Client\Provider\AdzunaProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-adzuna#usage), and as always, feel free to contact us if you'd like to get involved.
