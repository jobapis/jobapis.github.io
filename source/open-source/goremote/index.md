---
title: GoRemote RSS Feed Client
date: 2017-02-09 08:04:02
---

## Project Overview
Use the GoRemote Jobs Provider to connect your PHP application with the GoRemote job board RSS Feed.

- [Github](https://github.com/jobapis/jobs-goremote)
- [Packagist](https://packagist.org/packages/jobapis/jobs-goremote)
- [GoRemote Jobs](https://goremote.io/)

### Installation

Use composer: `composer require jobapis/jobs-goremote`

### Usage

GoRemote provides no search parameters, just a feed of all their latest jobs via RSS. In order to get the latest job listings, first create a query object.
 
```php
$query = new JobApis\Jobs\Client\Queries\GoRemoteQuery();
```

Then inject the query object into the provider.

```php
$client = new JobApis\Jobs\Client\Providers\GoRemoteProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
$jobs = $client->getJobs();
```

The `getJobs()` method will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects based on Schema.org's [JobPosting](https://schema.org/JobPosting) specification.

For more detailed documentation, see [this project's readme](https://github.com/jobapis/jobs-goremote)
