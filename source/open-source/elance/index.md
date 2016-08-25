---
title: Elance PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common Elance Provider to connect your PHP application with the Elance job board API.

- [Github](https://github.com/jobapis/jobs-elance)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-elance)
- [API Docs](https://www.elance.com/q/api2)

### Installation

Use composer: `composer require jobbrander/jobs-elance`

### Usage

Get the latest project manager jobs in Chicago:

```
$client = new JobBrander\Jobs\Client\Providers\Elance([
    'token' => 'ELANCE ACCESS TOKEN',
]);

$jobs = $client->setKeyword('project manager')
    ->getJobs(); 
```

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-elance#usage)
