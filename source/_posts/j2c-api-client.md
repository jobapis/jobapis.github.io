---
title: Jobs2Careers Job Board Api Client v.2 Released
date: 2017-02-14 12:13:55
tags:
- releases 
- clients
- jobs2careers
---

Jobs2Careers support has been on hold since last year's release of Jobs Common v2. Thanks to some help from [Samer Bechara](https://github.com/arbet) we have gotten the package up and running again. It is now supported by [Jobs Multi as well](https://github.com/jobapis/jobs-multi).

Get started using this API client by including the package in your project's composer file:
 
```
composer require jobapis/jobs-jobs2careers
```

As with all [Jobs Common](https://github.com/jobapis/jobs-common) providers, you first need to create a Query:

```php
$query = new JobApis\Jobs\Client\Queries\J2cQuery([
    'id' => YOUR_PUBLISHER_ID,
    'pass' => YOUR_PUBLISHER_PASSWORD,
    'q' => 'engineer',
    'l' => 'Chicago, IL',
]);
```

And inject it into the `J2cProvider`:

```php
$client = new JobApis\Jobs\Client\Providers\J2cProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-jobs2careers#usage), and as always, feel free to contact us if you'd like to get involved.
