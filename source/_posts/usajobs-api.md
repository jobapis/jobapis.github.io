---
title: USAJobs API Client now available
date: 2016-09-17 16:46:40
tags: 
- releases 
- clients
- usajobs
---

I've added a new PHP client for [USAJobs](https://github.com/jobapis/jobs-usajobs), and released it to work with v2 of the Jobs-Common project.

[USAJobs](https://www.usajobs.gov/) is one of the sources for the Government Jobs API, but their API has jobs that aren't necessarily collected by the [DigitalGov service](http://search.digitalgov.gov/developer/jobs.html), so if you're really interested in using government jobs in your application, this could be a great addition..

The basic usage is the same as most of our other providers:

### 1. Install the package via Composer

`composer require jobapis/jobs-usajobs`

### 2. Create a query object with all API parameters
```php
$query = new JobApis\Jobs\Client\Queries\UsajobsQuery([
    'Keyword' => 'engineering',
    'LocationName' => 'Chicago, IL',
    'AuthorizationKey' => YOUR_API_KEY,
]);
```

### 3. Inject the query object and get jobs

```php
$client = new JobApis\Jobs\Client\Provider\UsajobsProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-usajobs#usage)

