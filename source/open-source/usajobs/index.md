---
title: USAJobs PHP API Client
date: 2016-09-17 00:00:00
---

## Project Overview
Use the USAJobs Provider to connect your PHP application with the USAJobs job board API.

- [Github](https://github.com/jobapis/jobs-usajobs)
- [Packagist](https://packagist.org/packages/jobapis/jobs-usajobs)
- [API Docs](https://developer.usajobs.gov/Search-API/Overview)

### Installation

Use composer: `composer require jobapis/jobs-usajobs`

### Usage
Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\UsajobsQuery([
    'AuthorizationKey' => YOUR_API_KEY
]);
```

Or via the "set" method. All of the parameters documented can be added.

```php
// Add parameters via the set() method
$query->set('Keyword', 'engineering');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('LocationName', 'Chicago, IL')
    ->set('JobCategoryCode', '1234');
```
 
Then inject the query object into the provider.

```php
// Instantiating provider with a query object
$client = new JobApis\Jobs\Client\Provider\UsajobsProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-usajobs#usage)
