---
title: Dice PHP API Client
date: 2016-08-21 16:04:02
---

## Project Overview
Use the Jobs Common Dice Provider to connect your PHP application with the Dice job board API.

- [Github](https://github.com/jobapis/jobs-dice)
- [Packagist](https://packagist.org/packages/JobBrander/jobs-dice)
- [API Docs](http://www.dice.com/common/content/util/apidoc/jobsearch.html)

### Installation

Use composer: `composer require jobbrander/jobs-dice`

### Usage

Get the latest project manager jobs in Chicago:

```
$client = new JobBrander\Jobs\Client\Providers\Dice;

$jobs = $client->setKeyword('project manager')
    ->setCity('Chicago')
    ->getJobs(); 
```

For more detailed usage and documentation, see [this project's readme](https://github.com/JobBrander/jobs-dice#usage)
