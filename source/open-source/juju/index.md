---
title: Juju PHP API Client
date: 2016-10-03 16:04:02
---

## Project Overview
Use the Jobs Common Juju Provider to connect your PHP application with the Juju job board API.

- [Github](https://github.com/jobapis/jobs-juju)
- [Packagist](https://packagist.org/packages/jobapis/jobs-juju)
- [API Docs](http://www.juju.com/publisher/spec/)

### Installation

Use composer: `composer require jobapis/jobs-juju`

### Usage
Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\JujuQuery([
    'partnerid' => YOUR_PARTNER_ID
]);
```

Or via the "set" method. All of the parameters documented in Indeed's documentation can be added.

```php
// Add parameters via the set() method
$query->set('k', 'engineering');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('l', 'Chicago, IL')
    ->set('highlight', '1');
```
 
Then inject the query object into the provider.

```php
// Instantiating an IndeedProvider with a query object
$client = new JobApis\Jobs\Client\Provider\JujuProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

The `getJobs` method will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-juju#usage)
