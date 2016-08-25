---
title: Careercast PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common Careercast Provider to connect your PHP application with the Careercast job board API.

- [Github](https://github.com/jobapis/jobs-careercast)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-careercast)

### Installation

Use composer: `composer require jobbrander/jobs-careercast`

### Usage

Get the latest project manager jobs in Chicago:

```
$client = new JobBrander\Jobs\Client\Providers\Careercast;

$jobs = $client->setKeyword('project manager')
    ->setLocation('Chicago, Illinois, United States')
    ->getJobs(); 
```

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-careercast#usage)
