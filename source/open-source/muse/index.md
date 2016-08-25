---
title: Muse PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common Muse Provider to connect your PHP application with the Muse job board API.

- [Github](https://github.com/JobBrander/jobs-muse)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-muse)
- [API Docs](https://www.themuse.com/developers)

### Installation

Use composer: `composer require jobbrander/jobs-muse`

### Usage

Get the latest project manager jobs in Chicago:

```
$client = new JobBrander\Jobs\Client\Providers\Muse();

$jobs = $client->setCategory('Project & Product Management')
    ->setLocation('Chicago, IL')
    ->getJobs();
```

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-muse#usage)
