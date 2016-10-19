---
title: Adzuna PHP API Client
date: 2016-10-18 16:04:02
---

## Project Overview
Use the Adzuna Jobs Provider to connect your PHP application with the Adzuna job board API.

- [Github](https://github.com/jobapis/jobs-adzuna)
- [Packagist](https://packagist.org/packages/jobapis/jobs-adzuna)
- [API Docs](https://developer.adzuna.com/overview)

### Installation

Use composer: `composer require jobapis/jobs-adzuna`

### Usage
Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\AdjunaQuery([
    'app_key' => YOUR_KEY,
    'app_id' => YOUR_ID,
    'country' => 'gb',
]);
```

Or via the "set" method. All of the parameters documented in Indeed's documentation can be added.

```php
// Add parameters via the set() method
$query->set('what', 'engineering');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('where', 'London, UK')
    ->set('page', '2');
```
 
Then inject the query object into the provider.

```php
// Instantiating the provider with a query object
$client = new JobApis\Jobs\Client\Provider\AdzunaProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

The `getJobs` method will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-adzuna#usage).
