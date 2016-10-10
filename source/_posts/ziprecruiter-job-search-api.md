---
title: Ziprecruiter Job Search Client v1.0 Release
date: 2016-10-09 00:00:00
tags: 
- releases 
- clients
- ziprecruiter
---

Tonight we released a new version of our [PHP Ziprecruiter API provider](https://github.com/jobapis/jobs-ziprecruiter) supporting [version 2.0 of the Jobs Common project](https://github.com/jobapis/jobs-common).

This release now uses the two-object pattern (Query and Provider) that all v2 providers use, and it allows for queries using all supported Ziprecruiter URL parameters.

The basic usage is the same as most of our other providers:

### 1. Install the package via Composer

`composer require jobapis/jobs-ziprecruiter`

### 2. Create a query object with all API parameters
```php
$query = new JobApis\Jobs\Client\Queries\ZiprecruiterQuery([
    'search' => 'engineering',
    'location' => 'Chicago, IL',
]);
```

### 3. Inject the query object and get jobs

```php
$client = new JobApis\Jobs\Client\Provider\ZiprecruiterProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-ziprecruiter#usage)

