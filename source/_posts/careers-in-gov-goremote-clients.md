---
title: Careers in Government and GoRemote RSS Clients Released
date: 2017-02-09 07:33:19
tags: 
- releases 
- clients
- careers-in-government
- goremote
- rss
---

This month, we released two new job board clients: [CareersInGovernment.com](https://careersingovernment.com/) ([Github](https://github.com/jobapis/jobs-careersingov)) and [GoRemote.io](https://goremote.io/) ([Github](https://github.com/jobapis/jobs-goremote)). Both of these clients use RSS feeds to get the latest job listings.

Usage for each is pretty simple as there are no parameters that can be injected in the Query Objects.

### [Careers in Government](https://github.com/jobapis/jobs-careersingov)

Install [the package](https://packagist.org/packages/jobapis/jobs-careersingov) with Composer, and require the vendor file in your project. After the package is installed, you can get the latest listings in a couple lines of code:

```php
$client = new CareersInGovProvider(new CareersInGovQuery());
$jobs = $client->getJobs();
```

For more detailed documentation see this [project's readme file](https://github.com/jobapis/jobs-careersingov/blob/master/README.md).

### [GoRemote](https://github.com/jobapis/jobs-goremote)

Install [the package](https://packagist.org/packages/jobapis/jobs-goremote) with Composer, and require the vendor file in your project. After the package is installed, you can get the latest listings in a couple lines of code:

```php
$client = new GoRemoteProvider(new GoRemoteQuery());
$jobs = $client->getJobs();
```

For more detailed documentation see this [project's readme file](https://github.com/jobapis/jobs-goremote/blob/master/README.md).
