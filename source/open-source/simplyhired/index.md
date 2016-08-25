---
title: SimplyHired PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common SimplyHired Provider to connect your PHP application with the SimplyHired job board API.

- [Github](https://github.com/jobapis/jobs-simplyhired)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-simplyhired)

### Installation

Use composer: `composer require jobbrander/jobs-simplyhired`

### Usage

Get the latest project manager jobs in Chicago:

```
$client = new JobBrander\Jobs\Client\Providers\Simplyhired([
    'auth' => 'YOUR SIMPLYHIRED AUTHORIZATION KEY'
    'pshid' => 'YOUR SIMPLYHIRED PUBLISHER ID',
    'clip' => 'YOUR IP ADDRESS',
]);

$jobs = $client->setKeyword('project manager')
    ->setLocation('Chicago, IL')
    ->getJobs();
```

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-simplyhired#usage)
