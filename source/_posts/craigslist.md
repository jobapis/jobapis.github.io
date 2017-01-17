---
title: Craigslist Jobs RSS Feed Client for PHP
date: 2017-01-12 15:21:31
tags:
- releases 
- clients
- craigslist
- rss
---

Today we released our 17th job board client using version 2.0 of the [Jobs Common framework](https://github.com/jobapis/jobs-common), a Craigslist job search RSS feed client. Using this client, you can quickly access the job search RSS feed on Craigslist in your PHP projects. Here's an example of the library in action:

### Usage

Install the package using Composer:

```
composer require jobapis/jobs-craigslist
```

Then create a query object with all the parameters you'd like to use:

```php
// Add parameters to the query via the constructor
$query = new JobApis\Jobs\Client\Queries\CraigslistQuery([
    'location' => 'chicago',    // Craigslist location. Full list of locations here: https://sites.google.com/site/clsiteinfo/city-site-code-sort
    'query' => 'sales',         // Search query
    's' => '100',               // Offset results
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

Check out more examples or [contribute to the project on Github](https://github.com/jobapis/jobs-craigslist).
