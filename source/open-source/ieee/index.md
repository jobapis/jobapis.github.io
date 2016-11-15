---
title: IEEE JobSite PHP API Client
date: 2016-10-29 14:12:55
---

## Project Overview
Use the IEEE JobSite Provider to connect your PHP application with the IEEE job board.

- [Github](https://github.com/jobapis/jobs-ieee)
- [Packagist](https://packagist.org/packages/jobapis/jobs-ieee)
- [IEEE Site](http://careers.ieee.org/)

### Installation

Use composer: `composer require jobapis/jobs-ieee`

## Usage
Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\IeeeQuery();
```

Or via the "set" method. All of the parameters documented in Indeed's documentation can be added.

```php
// Add parameters via the set() method
$query->set('keyword', 'engineering');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('location', 'Chicago, IL')
    ->set('radius', '50');
```
 
Then inject the query object into the provider.

```php
// Instantiating a provider with a query object
$client = new JobApis\Jobs\Client\Provider\IeeeProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

The `getJobs` method will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-ieee#usage).
