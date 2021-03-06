---
title: Careerbuilder PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Careerbuilder Jobs Provider to connect your PHP application with the Careerbuilder job board API.

- [Github](https://github.com/jobapis/jobs-careerbuilder)
- [Packagist](https://packagist.org/packages/jobapis/jobs-careerbuilder)
- [API Docs](http://developer.careerbuilder.com/)

### Installation

Use composer: `composer require jobapis/jobs-careerbuilder`

### Usage
Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\CareerbuilderQuery([
    'DeveloperKey' => YOUR_API_ID
]);
```

Or via the "set" method. All of the parameters documented in Indeed's documentation can be added.

```php
// Add parameters via the set() method
$query->set('Keywords', 'engineering');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('FacetCity', 'Chicago')
    ->set('FacetState', 'IL');
```
 
Then inject the query object into the provider.

```php
// Instantiating provider with a query object
$client = new JobApis\Jobs\Client\Provider\CareerbuilderProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-careerbuilder#usage)
