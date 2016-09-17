---
title: Querying multiple job board APIs at once
date: 2016-09-11 15:28:59
tags:
- releases
- jobs-multi
---

Today marks the first pre-release of [Jobs-Multi](https://github.com/jobapis/jobs-multi), a package intented to help you access multiple job board APIs in PHP with less work.

Where [Jobs-Common](https://github.com/jobapis/jobs-common) standardizes the _output_ of each job board, Jobs-Multi helps standardize the _input_, giving users access to three setters that enable you to build multiple Queries and then retrieve all the results at the same time.

What does this mean in practice? With Jobs-Multi you can do things like:

```php
$client = new JobsMulti([
    'Dice' => [],
    'Govt' => [],
    'Github' => [],
]);
$jobs = $client->setKeyword('training')
   ->setLocation('chicago, il')
   ->setPage(1, 10)
   ->getAllJobs();
```

That final `$jobs` variable contains an array of all jobs matching the provided criteria from [Dice](https://github.com/jobapis/jobs-dice), [Government Jobs](https://github.com/jobapis/jobs-govt), and [Github](https://github.com/jobapis/jobs-github) in one go.

You can access more providers and you also have the option to query each one individually. See the [jobs-multi repo on Github for more details](https://github.com/jobapis/jobs-multi).
