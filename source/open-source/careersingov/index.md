---
title: CareersInGovernment.com RSS API Client
date: 2017-01-17 16:04:02
---

## Project Overview
Use the Jobs Common Careers in Government Provider to connect your PHP application with the job board's RSS feed.

- [Github](https://github.com/jobapis/jobs-careersingov)
- [Packagist](https://packagist.org/packages/jobapis/jobs-careersingov)
- [CareersInGovernment.com](https://careersingovernment.com/)

### Installation

To install, use composer:

```
composer require jobapis/jobs-careersingov
```

### Usage
Careers in Government provides no search parameters, just a feed of all their latest jobs via RSS.

In order to grab jobs, first create a query object:
 
```php
// Instantiate the query object
$query = new JobApis\Jobs\Client\Queries\CareersInGovQuery();
```

Then inject the query object into the provider.

```php
// Instantiating a provider with a query object
$client = new JobApis\Jobs\Client\Provider\CareersInGovProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

The `getJobs` method will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-careersingov#usage)
