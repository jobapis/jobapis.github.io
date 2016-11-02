---
title: Jobinventory PHP RSS Client
date: 2016-10-29 14:12:55
---

## Project Overview
Use the Jobinventory Jobs Provider to connect your PHP application with the Jobinventory job board RSS feed.

- [Github](https://github.com/jobapis/jobs-jobinventory)
- [Packagist](https://packagist.org/packages/jobapis/jobs-jobinventory)
- [Jobinventory Site](http://www.jobinventory.com/)

### Installation

Use composer: `composer require jobapis/jobs-jobinventory`

### Usage
Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\JobinventoryQuery(['p' => 2]);
```

Or via the "set" method. All of the parameters documented in Indeed's documentation can be added.

```php
// Add parameters via the set() method
$query->set('q', 'engineering');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('l', 'Chicago, IL')
    ->set('limit', '20');
```
 
Then inject the query object into the provider.

```php
// Instantiating a provider with a query object
$client = new JobApis\Jobs\Client\Provider\JobinventoryProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

The `getJobs` method will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-jobinventory#usage).
