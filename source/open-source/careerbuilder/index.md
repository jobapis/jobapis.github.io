---
title: Careerbuilder PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common Careerbuilder Jobs Provider to connect your PHP application with the Careerbuilder job board API.

- [Github](https://github.com/jobapis/jobs-careerbuilder)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-careerbuilder)
- [API Docs](http://developer.careerbuilder.com/)

### Installation

Use composer: `composer require jobbrander/jobs-careerbuilder`

### Usage

Get the latest project manager jobs in Chicago:

```
$client = new JobBrander\Jobs\Client\Providers\Careerbuilder([
    'DeveloperKey' => 'YOUR CAREERBUILDER DEV KEY',
]);

$jobs = $client->setKeyword('project manager')
    ->setCity('Chicago')
    ->getJobs(); 
```

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-careerbuilder#usage)
