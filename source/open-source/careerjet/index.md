---
title: Careerjet PHP API Client
date: 2016-11-09 16:04:02
---

## Project Overview
Use the Careerjet Jobs Provider to connect your PHP application with the Careerjet job board API.

- [Github](https://github.com/jobapis/jobs-careerjet)
- [Packagist](https://packagist.org/packages/jobapis/jobs-careerjet)
- [API Docs](http://www.careerjet.com/partners/)

### Installation

Use composer: `composer require jobapis/jobs-careerjet`

### Usage
Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\CareerjetQuery([
    'affid' => YOUR_AFFILIATE_ID
]);
```

Or via the "set" method. All of the parameters documented in Indeed's documentation can be added.

```php
// Add parameters via the set() method
$query->set('keywords', 'engineering');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('location', 'Chicago, IL')
    ->set('page', '2');
    ->set('pagesize', '100');
```
 
Then inject the query object into the provider.

```php
// Instantiating an IndeedProvider with a query object
$client = new JobApis\Jobs\Client\Provider\CareerjetProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

The `getJobs` method will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-careerjet#usage).
