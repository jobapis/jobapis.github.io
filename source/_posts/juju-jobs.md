---
title: Juju job board API client now available in Jobs Common v2
date: 2016-10-03 21:29:24
tags:
- releases 
- clients
- juju
---

In an effort to release 21 job board clients using v2 of the [Jobs Common package](https://github.com/jobapis/jobs-common) by the end of 2016, I'm excited to announce the release of our 8th job board client - Juju Jobs.

[Juju](http://www.juju.com/) is a job search engine that aggregates from many sources to be one of the largest job providers in the United States. We previously offered support for v1 of Jobs Common, but with the new release using v2, the usage has changed:
 
### 1. Install the package via Composer

`composer require jobapis/jobs-juju`

### 2. Create a query object with all API parameters
```php
$query = new JobApis\Jobs\Client\Queries\JujuQuery([
    'k' => 'engineering', // Keyword
    'l' => 'chicago', // Location
    'h' => '0', // Highlighting off
]);
```

### 3. Inject the query object and get jobs

```php
$client = new JobApis\Jobs\Client\Provider\JujuProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-juju#usage)
