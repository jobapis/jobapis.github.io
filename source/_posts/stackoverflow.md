---
title: Stack Overflow Job Board Client
date: 2016-11-29 13:08:52
tags:
- releases 
- clients
- stack overflow
- rss
---

Stack Overflow is widely recognized for being one of the best Q&A sites for developers. This package makes it easy to access [their job listings](https://stackoverflow.com/jobs) via the site's RSS feed and the [Jobs Common](https://github.com/jobapis/jobs-common) project. Use of this package is similar to most other packages supported by Jobs Common:

First, create a Query object:
```php
$query = new JobApis\Jobs\Client\Queries\StackoverflowQuery([
    'q' => 'engineering',
    'l' => 'Chicago, IL',
    'pg' => '2',
]);
```
*For a full list of supported query options, [see this file](https://github.com/jobapis/jobs-stackoverflow/blob/master/src/Queries/StackoverflowQuery.php).*

And inject it into the `StackoverflowProvider`:

```php
$client = new JobApis\Jobs\Client\Provider\StackoverflowProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-stackoverflow#usage), and as always, feel free to contact us if you have any questions or comments.
