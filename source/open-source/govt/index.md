---
title: Government Jobs PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Government Jobs Provider to connect your PHP application with the Government job board API.

- [Github](https://github.com/jobapis/jobs-govt)
- [Packagist](https://packagist.org/packages/jobapis/jobs-govt)
- [API Docs](http://search.digitalgov.gov/developer/jobs.html)

### Installation

Use composer: `composer require jobapis/jobs-govt`

### Usage

Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\GovtQuery([
    'hl' => '1'
]);
```

Or via the "set" method. All of the parameters documented in the API's documentation can be added.

```php
// Add parameters via the set() method
$query->set('query', 'engineering');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('size', '100')
    ->set('from', '200');
```

*Note: The government jobs API doesn't support adding location as a parameter, but their keyword or lat_lon parameters can be used for this purpose.* 

Then inject the query object into the provider.

```php
// Instantiating provider with a query object
$client = new JobApis\Jobs\Client\Provider\GovtProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-govt#usage)
