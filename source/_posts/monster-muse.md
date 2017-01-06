---
title: Monster.com RSS Client and theMuse.com API Client Released
date: 2017-01-06 14:28:11
tags:
- releases 
- clients
- monster
- muse
---

## Monster.com Jobs RSS feed client
Monster.com's official API is closed to most users (they have not responded to multiple requests for access), but their RSS feed provides a small subset of their jobs. Unfortunately, results are only from the past 24 hours, so this client won't work for all applications. Using the client is pretty much the same as most RSS feed providers we support:

### 1. Install the package via Composer

`composer require jobapis/jobs-monster`

### 2. Create a query object with all API parameters
```php
$query = new JobApis\Jobs\Client\Queries\MonsterQuery([
    'q' => 'engineering', // Keyword
    'where' => 'chicago', // Location
    'p' => '1', // Page number
]);
```

### 3. Inject the query object and get jobs

```php
$client = new JobApis\Jobs\Client\Provider\MonsterProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-monster#usage)
 
## The Muse Jobs API client
We also re-released our Muse API client with support for Jobs Common v.2 and the Muse's v.2 of their API. Their API still does not support a true "keyword" search, but the category field allows you to search by types of jobs. Usage is similar to the above client:

### 1. Install the package via Composer

`composer require jobapis/jobs-muse`

### 2. Create a query object with all API parameters
```php
$query = new JobApis\Jobs\Client\Queries\MuseQuery([
    'category' => 'Engineering',
    'location' => 'Chicago, IL',
]);
```

### 3. Inject the query object and get jobs

```php
$client = new JobApis\Jobs\Client\Provider\MuseProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-muse#usage)
