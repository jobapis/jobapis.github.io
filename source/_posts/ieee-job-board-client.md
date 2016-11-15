---
title: IEEE JobSite Client Released
date: 2016-11-15 16:34:20
tags:
- releases 
- clients
- ieee
---

The [IEEE](https://www.ieee.org/index.html) is a professional engineering organization with the largest membership of any technical organization in the world. Their [job board](http://careers.ieee.org/) is mostly geared towards engineers, especially computer and electrical engineers, but a variety of career paths may be represented. Unfortunately, their API is not documented, but can be accessed by appending `&format=json` to most search queries on the site.

Based on this knowledge and some testing I was able to create a [job board API client for IEEE's JobSite](https://github.com/jobapis/jobs-ieee) and it is now the 18th job board API client supported by our organization.

To start using the IEEE job board API client, install the package via composer:
 
Next, create a Query object:
```php
$query = new JobApis\Jobs\Client\Queries\IeeeQuery([
    'keyword' => 'engineering',
    'location' => 'Chicago, IL',
    'rows' => '50',
]);
```
*For a full list of supported query options, [see this file](https://github.com/jobapis/jobs-ieee/blob/master/src/Queries/IeeeQuery.php).*

And inject it into the `IeeeProvider`:

```php
$client = new JobApis\Jobs\Client\Provider\IeeeProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-ieee#usage), and as always, feel free to contact us if you have any questions or comments.
