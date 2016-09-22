---
title: Careercast PHP API Client
date: 2016-09-22 00:00:00
---

## Project Overview
Use the Jobs Common Careercast Provider to connect your PHP application with the Careercast job board API.

- [Github](https://github.com/jobapis/jobs-careercast)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-careercast)

### Installation

Use composer: `composer require jobapis/jobs-careercast`

### Usage
Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\CareercastQuery([
    'keyword' => 'engineering'
]);
```

Or via the "set" method. All of the parameters documented can be added.

```php
// Add parameters via the set() method
$query->set('location', 'Chicago, IL');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('company', 'General Electric')
    ->set('page', '2');
```
 
Then inject the query object into the provider.

```php
// Instantiating provider with a query object
$client = new JobApis\Jobs\Client\Provider\CareercastProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-careercast#usage)
