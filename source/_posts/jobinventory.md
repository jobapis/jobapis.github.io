---
title: Jobinventory RSS Feed Provider Released
date: 2016-10-29 14:12:55
tags:
- releases 
- clients
- jobinventory
- rss
---

While most of the job board clients supported by [Jobs Common](https://github.com/jobapis/jobs-common) are for job boards with full-service APIs, Jobinventory only provides an XML RSS feed for consumption. Today we released our first version of the PHP RSS client for Jobinventory, and you can download it [here on Github](https://github.com/jobapis/jobs-jobinventory).

Use of the Jobinventory provider follows much the same pattern as our other job board providers.

First, create a Query object:
```php
$query = new JobApis\Jobs\Client\Queries\JobinventoryQuery([
    'q' => 'engineering',
    'l' => 'Chicago, IL',
    'limit' => '100',
]);
```
*For a full list of supported query options, [see this file](https://github.com/jobapis/jobs-jobinventory/blob/master/src/Queries/JobinventoryQuery.php).*

And inject it into the `JobinventoryProvider`:

```php
$client = new JobApis\Jobs\Client\Provider\JobinventoryProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-jobinventory#usage), and as always, feel free to contact us if you have any questions or comments.
