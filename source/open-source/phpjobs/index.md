---
title: PHPJobs.com API Client
date: 2017-01-17 16:04:02
---

## Project Overview
Use the Jobs Common PHPJobs Provider to connect your PHP application with the Muse job board API.

- [Github](https://github.com/jobapis/jobs-phpjobs)
- [Packagist](https://packagist.org/packages/jobapis/jobs-phpjobs)
- [PHPJobs.com](http://www.phpjobs.com/)

### Installation

To install, use composer:

```
composer require jobapis/jobs-phpjobs
```

### Usage
Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\PhpjobsQuery();
```

Or via the "set" method. All of the parameters documented in Indeed's documentation can be added.

```php
// Add parameters via the set() method
$query->set('search_string', 'zend');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('country_code', 'us')
    ->set('search_string', 'laravel');
```
 
Then inject the query object into the provider.

```php
// Instantiating a provider with a query object
$client = new JobApis\Jobs\Client\Provider\PhpjobsProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

The `getJobs` method will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-phpjobs#usage)
