---
title: Stack Overflow Job Board Client
date: 2016-11-29 13:08:52
---

## Project Overview
Use the Stack Overflow Jobs Provider to connect your PHP application with the Stack Overflow job board RSS feed.

- [Github](https://github.com/jobapis/jobs-stackoverflow)
- [Packagist](https://packagist.org/packages/jobapis/jobs-stackoverflow)
- [Stack Overflow Jobs](https://stackoverflow.com/jobs)

### Installation

Use composer: `composer require jobapis/jobs-stackoverflow`

### Usage
Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\StackoverflowQuery();
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
    ->set('pg', '2');
```
 
Then inject the query object into the provider.

```php
// Instantiating a provider with a query object
$client = new JobApis\Jobs\Client\Provider\StackoverflowProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

The `getJobs` method will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-stackoverflow#usage).
