---
title: JobsMulti - the Ultimate Job Board API Client - Version 1.0 Release
date: 2016-12-01 09:42:27
tags:
- releases 
- jobs multi
- clients
---

Today we are excited to announce the release of version 1.0, the first stable release, of [JobsMulti](https://github.com/jobapis/jobs-multi).

## What is [JobsMulti](https://github.com/jobapis/jobs-multi)?
JobsMulti is the ultimate job board API client. With a few lines of code, you can grab the latest jobs from up to 13 job boards (as of this writing), with our list of supported job boards growing every month. So, instead of writing code to query each job board individually, developers can get results from multiple job boards with just one client.

The code speaks for itself, so here's an example of using JobsMulti v.1.0:

```php
// Include as many or as few providers as you want. Just be sure to include any required keys.
$providers = [
    'Careerbuilder' => [
        'DeveloperKey' => '<YOUR DEVELOPER KEY>',
    ],
    'Careercast' => [],
    'Careerjet' => [
        'affid' => '<YOUR AFFILIATE ID>',
    ],
    'Github' => [],
    'Govt' => [],
    'Ieee' => [],
    'Indeed' => [
        'publisher' => '<YOUR PUBLISHER ID>',
    ],
    'Jobinventory' => [],
    'Juju' => [
        'partnerid' => '<YOUR PARTNER ID>',
    ],
    'Stackoverflow' => [],
    'Usajobs' => [
        'AuthorizationKey' => '<YOUR API KEY>',
    ],
    'Ziprecruiter' => [
        'api_key' => '<YOUR API KEY>',
    ],
];

// Instantiate a new JobsMulti client
$client = new JobsMulti($providers);

// Set the parameters: Keyword, Location, Page
$client->setKeyword('engineering')
    ->setLocation('chicago, il')
    ->setPage(1, 10);

// And include an array of options if you'd like
$options = [
    'maxAge' => 30,              // Maximum age (in days) of listings
    'maxResults' => 100,         // Maximum number of results
    'orderBy' => 'datePosted',   // Field to order results by
    'order' => 'desc',           // Order ('asc' or 'desc')
];

// Finally, get all the jobs in a single Collection
$jobs = $client->getAllJobs($options);
```

More details can be found on the [JobsMulti landing page](/open-source/jobs-multi) and in the [Readme](https://github.com/jobapis/jobs-multi/blob/master/README.md). This project is free and open source, so if it helps you out, let us hear about it on Twitter: [@jobapis](https://twitter.com/jobapis).
