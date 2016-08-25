---
title: Government Jobs PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common Government Jobs Provider to connect your PHP application with the Government job board API.

- [Github](https://github.com/jobapis/jobs-govt)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-govt)
- [API Docs](http://search.digitalgov.gov/developer/jobs.html)

### Installation

Use composer: `composer require jobbrander/jobs-govt`

### Usage

Get the latest project manager jobs in Chicago:

```
$client = new JobBrander\Jobs\Client\Providers\Govt;

$jobs = $client->setQuery('project manager in chicago')
    ->getJobs(); 
```

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-govt#usage)
