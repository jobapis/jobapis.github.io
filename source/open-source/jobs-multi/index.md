---
title: JobsMulti - The Ultimate Job Board API Client
date: 2016-12-01 09:42:27
---

## Project Overview
JobsMulti is the ultimate job board API client. With this package, PHP developers can access 12+ job board APIs with a single client and a few lines of code.

- [Github](https://github.com/jobapis/jobs-multi)
- [Packagist](https://packagist.org/packages/jobapis/jobs-multi)

### Installation

Use composer: `composer require jobapis/jobs-multi`

### Usage

To get the latest "engineering jobs" in Chicago from Github, IEEE Job Board, and StackOverflow, here's what you would do:

```php
$providers = [
    'Github' => [],
    'Ieee' => [],
    'Stackoverflow' => [],
];

// Instantiate a new JobsMulti client
$client = new JobsMulti($providers);

// Set the parameters: Keyword, Location
$client->setKeyword('engineering')
    ->setLocation('chicago, il');

// And include an array of options if you'd like
$options = [
    'maxAge' => 30,              // Maximum age (in days) of listings
    'maxResults' => 100,         // Maximum number of results
    'orderBy' => 'datePosted',   // Field to order results by
    'order' => 'desc',           // Order ('asc' or 'desc')
];

// Finally, retrieve the jobs
$jobs = $client->getAllJobs($options);
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) containing many [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

### Advanced Usage
See the [Readme](https://github.com/jobapis/jobs-multi/blob/master/README.md).

### Job Boards Supported
See the [Readme](https://github.com/jobapis/jobs-multi/blob/master/README.md).
