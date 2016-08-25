---
title: Authentic Jobs PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common Authentic Jobs Provider to connect your PHP application with the Authentic job board API.

- [Github](https://github.com/jobapis/jobs-authenticjobs)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-authenticjobs)
- [API Docs](https://authenticjobs.com/api/)

### Installation

Use composer: `composer require jobbrander/jobs-authenticjobs`

### Usage

Get the latest project manager jobs in Chicago:

```
$client = new JobBrander\Jobs\Client\Providers\AuthenticJobs([
   'key' => 'YOUR API KEY',
]);
$jobs = $client->setKeyword('project manager')
   ->setCity('Chicago')
   ->getJobs();
```

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-authenticjobs#usage)
