title: Github Jobs now available in Jobs Common v2
date: 2016-09-07 20:52:03
---

The [Github Jobs API provider](https://github.com/jobapis/jobs-github) has hit a version 1.0 release, which is now compatible with [Jobs Common v2](http://www.jobapis.com/2016/09/03/jobs-common-v2-release/).

If you're not sure what that means, basically it just means you can access jobs from Github's job board as described below.

### 1. Install the package via Composer

`composer require jobapis/jobs-github`

### 2. Create a query object with all API parameters
```php
$query = new JobApis\Jobs\Client\Queries\GithubQuery([
    'search' => 'engineering',
    'location' => 'chicago',
    'page' => '1',
]);
```

### 3. Inject the query object and get jobs

```php
$client = new JobApis\Jobs\Client\Provider\GithubProvider($query);
$jobs = $client->getJobs();
```

This will return a [Collection](https://github.com/jobapis/jobs-common/blob/master/src/Collection.php) of [Job](https://github.com/jobapis/jobs-common/blob/master/src/Job.php) objects.

For more detailed usage and documentation, see [this project's readme](https://github.com/jobapis/jobs-github#usage)
