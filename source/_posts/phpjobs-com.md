---
title: PHPJobs.com RSS Client Released
date: 2017-01-17 15:21:31
tags:
- releases 
- clients
- phpjobs
- rss
---

We now support PHPJobs.com's RSS feed of job using the [Jobs Common framework](https://github.com/jobapis/jobs-common). With this client, you can quickly access the job search RSS feed on PHPJobs.com in your projects. Here's an example of the library in action:

### Usage

Install the package using Composer:

```
composer require jobapis/jobs-phpjobs
```

Then create a query object with all the parameters you'd like to use:

```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\PhpjobsQuery([
    'search_string' => 'zend'
]);
```
 
And inject the query object into the provider:

```php
$client = new JobApis\Jobs\Client\Provider\CraigslistProvider($query);
```

Finally, call the "getJobs" method to retrieve results:

```php
// Get a Collection of Jobs
$jobs = $client->getJobs();
```

Check out more examples or [contribute to the project on Github](https://github.com/jobapis/jobs-phpjobs).
