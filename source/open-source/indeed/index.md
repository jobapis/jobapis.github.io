---
title: Indeed PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common Indeed Provider to connect your PHP application with the Indeed job board API.

- [Github](https://github.com/jobapis/jobs-indeed)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-indeed)
- [API Docs](http://www.indeed.com/jsp/apiinfo.jsp)

### Installation

Use composer: `composer require jobbrander/jobs-indeed`

### Usage

Get the latest project manager jobs in Chicago:

```
$client = new JobBrander\Jobs\Client\Providers\Indeed([
    'publisher' => 'YOUR INDEED PUBLISHER ID',
    'format' => 'json',
]);

$jobs = $client->setKeyword('project manager')
    ->setCity('Chicago')
    ->getJobs(); 
```

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-indeed#usage)
