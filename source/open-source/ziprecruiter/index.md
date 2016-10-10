---
title: ZipRecruiter PHP API Client
date: 2016-10-09 00:04:02
---

## Project Overview
Use the Jobs Common ZipRecruiter Provider to connect your PHP application with the ZipRecruiter job board API.

- [Github](https://github.com/jobapis/jobs-ziprecruiter)
- [Packagist](https://packagist.org/packages/jobapis/jobs-ziprecruiter)
- [API Docs](https://www.zipalerts.com/user/integration/api)

### Installation

Use composer: `composer require jobapis/jobs-ziprecruiter`

### Usage

Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\ZiprecruiterQuery([
    'api_key' => YOUR_API_KEY
]);
```

Or via the "set" method. All of the parameters documented in Indeed's documentation can be added.

```php
// Add parameters via the set() method
$query->set('search', 'engineering');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('location', 'Chicago, IL')
    ->set('jobs_per_page', '100');
```
 
Then inject the query object into the provider.

```php
// Instantiating an IndeedProvider with a query object
$client = new JobApis\Jobs\Client\Provider\ZiprecruiterProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

The `getJobs` method will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-ziprecruiter#usage)
