---
title: Monster.com PHP RSS Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common Monster Provider to connect your PHP application with the Monster.com job board RSS feed.

- [Github](https://github.com/jobapis/jobs-muse)
- [Packagist](https://packagist.org/packages/jobapis/jobs-muse)
- [Monster](https://www.monster.com/)

### Installation

To install, use composer:

```
composer require jobapis/jobs-monster
```

### Usage
Create a Query object and add all the parameters you'd like via the constructor.

*Note: The Monster RSS feed only provides jobs from the past 24 hours.*
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\MonsterQuery();
```

Or via the "set" method. All of the parameters documented in Indeed's documentation can be added.

```php
// Add parameters via the set() method
$query->set('q', 'engineering');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('where', 'Chicago, IL')
    ->set('page', '2');
```
 
Then inject the query object into the provider.

```php
// Instantiating a provider with a query object
$client = new JobApis\Jobs\Client\Provider\MonsterProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

The `getJobs` method will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-monster#usage)
