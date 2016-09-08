---
title: Github Jobs PHP API Client
date: 2016-09-07 16:04:02
---

## Project Overview
This package provides [Github Jobs API](https://jobs.github.com/api)
support for the JobBrander's [Jobs Client](https://github.com/JobBrander/jobs-common).

- [Github](https://github.com/jobapis/jobs-github)
- [Packagist](https://packagist.org/packages/jobapis/jobs-github)
- [API Docs](https://jobs.github.com/api)

### Installation

Use composer: `composer require jobapis/jobs-github`

### Usage

Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\GithubQuery([
    'search' => 'engineering'
]);
```

Or via the "set" method. All of the parameters documented in the API's documentation can be added.

```php
// Add parameters via the set() method
$query->set('location', 'Chicago, IL');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('page', '2')
    ->set('full_time', 'true');
```
 
Then inject the query object into the provider.

```php
// Instantiating provider with a query object
$client = new JobApis\Jobs\Client\Provider\GithubProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-github#usage)
