---
title: Dice PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Dice Jobs Provider to connect your PHP application with the Dice job board API.

- [Github](https://github.com/jobapis/jobs-dice)
- [Packagist](https://packagist.org/packages/jobapis/jobs-dice)
- [API Docs](http://www.dice.com/common/content/util/apidoc/jobsearch.html)

### Installation

Use composer: `composer require jobapis/jobs-dice`

### Usage
Create a Query object and add all the parameters you'd like via the constructor.
 
```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\DiceQuery([
    'text' => 'engineering'
]);
```

Or via the "set" method. All of the parameters documented in the API's documentation can be added.

```php
// Add parameters via the set() method
$query->set('skill', 'soldering');
```

You can even chain them if you'd like.

```php
// Add parameters via the set() method
$query->set('state', 'Illinois')
    ->set('city', 'Chicago')
    ->set('country', 'United States');
```
 
Then inject the query object into the provider.

```php
// Instantiating provider with a query object
$client = new JobApis\Jobs\Client\Provider\DiceProvider($query);
```

And call the "getJobs" method to retrieve results.

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-dice#usage)
