---
title: Jobs2Careers PHP API Client
date: 2017-02-14 16:04:02
---

## Project Overview
Use the Jobs Common Jobs2Careers Provider to connect your PHP application with the Jobs2Careers job board API.

- [Github](https://github.com/jobapis/jobs-jobs2careers)
- [Packagist](https://packagist.org/packages/jobapis/jobs-jobs2careers)
- [API Docs](http://www.jobs2careers.com/publisher_services.php)

### Installation

Use composer: `composer require jobapis/jobs-jobs2careers`

### Usage

Get the latest project manager jobs in Chicago:

```
$query = new JobApis\Jobs\Client\Queries\J2cQuery([
    'id' => 'Jobs2Careers Partner ID',
    'pass' => 'Jobs2Careers Password',
    'q' => 'project manager',
    'l' => 'Chicago, IL',
]);

$client = new JobApis\Jobs\Client\Providers\J2cProvider($query);

$jobs = $client->getJobs();
```

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-jobs2careers#usage)
