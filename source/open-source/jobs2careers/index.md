---
title: Jobs2Careers PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common Jobs2Careers Provider to connect your PHP application with the Jobs2Careers job board API.

- [Github](https://github.com/jobapis/jobs-jobs2careers)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-jobs2careers)
- [API Docs](http://www.jobs2careers.com/publisher_services.php)

### Installation

Use composer: `composer require jobbrander/jobs-jobs2careers`

### Usage

Get the latest project manager jobs in Chicago:

```
$client = new JobBrander\Jobs\Client\Providers\J2c([
    'id' => 'Jobs2Careers Partner ID',
    'pass' => 'Jobs2Careers Password'
]);

$jobs = $client->setKeyword('project manager')
    ->setLocation('Chicago, IL')
    ->getJobs();
```

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-jobs2careers#usage)
