---
title: CareerCast API v1.0 Release Announcement
date: 2016-09-22 00:00:00
tags: 
- releases 
- clients
- careercast
---

The latest job board now supporting [version 2.0 of the Jobs Common project](https://github.com/jobapis/jobs-common) is the re-released [Careercast API client](https://github.com/jobapis/jobs-careercast), which just reached version 1.0 today.

This re-release offers most of the same functionality as the version 0 release, but defaults to JSON responses instead of XML. This allows for much richer data from the Careercast API.

Unfortunately, Careercast's API is not official or documented, so the setters are limited, and it appears that pagination doesn't work.

The basic usage is the same as most of our other providers:

### 1. Install the package via Composer

`composer require jobapis/jobs-careercast`

### 2. Create a query object with all API parameters
```php
$query = new JobApis\Jobs\Client\Queries\CareercastQuery([
    'keyword' => 'engineering',
    'location' => 'Chicago, IL',
]);
```

### 3. Inject the query object and get jobs

```php
$client = new JobApis\Jobs\Client\Provider\CareercastProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-careercast#usage)

