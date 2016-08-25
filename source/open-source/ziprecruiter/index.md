---
title: ZipRecruiter PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common ZipRecruiter Provider to connect your PHP application with the ZipRecruiter job board API.

- [Github](https://github.com/JobBrander/jobs-ziprecruiter)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-ziprecruiter)
- [API Docs](http://www.dice.com/common/content/util/apidoc/jobsearch.html)

### Installation

Use composer: `composer require jobbrander/jobs-ziprecruiter`

### Usage

Get the latest project manager jobs in Chicago:

```
$client = new JobBrander\Jobs\Client\Providers\Ziprecruiter([
    'api_key' => 'YOUR ZIPRECRUITER API KEY'
]);

$jobs = $client->setKeyword('project manager')
    ->setLocation('Chicago, IL')
    ->getJobs();
```

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-ziprecruiter#usage)
