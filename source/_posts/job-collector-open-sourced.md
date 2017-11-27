---
title: Our Job Board Data Collector is Open Source
date: 2017-11-27 00:00:00
tags:
- job boards
- collector
---

We've been running the Jobs Hub data collection service for [close to a year now](/2017/03/27/jobs-hub-release/), and so far, it's the only software we support that's not open source. As of today, that is changing.

You can now run your very own version of our job board data collector for free [by installing and running our open source job collection project](https://github.com/jobapis/collector). Here's a little more about how the project works:

## Why?

When I started work on JobApis, my goal was to standardize data from job boards. At some point, it became obvious that I'd need to collect this data from job boards and store it temporarily in a database in order to access it, analyze it, and learn more about the jobs being posted. The JobApis Collector is simply a wrapper around [JobsMulti](https://github.com/jobapis/jobs-multi) that allows you to dump jobs in Algolia as you collect them.

## How it works

Unfortunately, there's not an easy way to get _every_ job from every job board supported by JobsMulti, so the approach this project takes is to use a list of search terms to search each job board. The terms can include a location and keyword as well as timestamps for when they were created, collected, and requested for collection. These objects are stored in Algolia:

```json
{
  "keyword": "Retail Sales Associate",
  "location": "Orlando, FL",
  "created_at": 1501081885,
  "last_collection_requested_at": 1511550912,
  "last_collection_completed_at": 1511550923,
  "objectID": "354994470"
}
```

Each time the collector runs, it gets the term that was least recently requested for collection and queues up a request to collect it. Each collection run uses JobsMulti to get all of the latest jobs from all the jobs boards supported and saves each to Algolia. The jobs use our standard job object, and look something like this:

```json
{
      "alternateName": null,
      "baseSalary": null,
      "company": "ALDI",
      "datePosted": "2017-11-23",
      "description": "Store <b>Manager</b> Trainee – <b>Retail</b> Management (Customer Service) As a <b>Manager</b> Trainee at ALDI, you’ll never experience the same day twice....",
      "educationRequirements": null,
      "employmentType": null,
      "endDate": null,
      "experienceRequirements": null,
      "hiringOrganization": {
        "address": {
          "addressCountry": null,
          "addressLocality": "Orlando",
          "addressRegion": "FL",
          "postalCode": "Orlando, FL",
          "postOfficeBoxNumber": null,
          "streetAddress": null
        },
        "email": null,
        "logo": null,
        "telephone": null,
        "alternateName": null,
        "description": null,
        "name": "ALDI",
        "url": null
      },
      "incentiveCompensation": null,
      "industry": null,
      "javascriptAction": null,
      "javascriptFunction": null,
      "jobBenefits": null,
      "jobLocation": {
        "address": {
          "addressCountry": null,
          "addressLocality": "Orlando",
          "addressRegion": "FL",
          "postalCode": "Orlando, FL",
          "postOfficeBoxNumber": null,
          "streetAddress": null
        },
        "geo": {
          "latitude": null,
          "longitude": null,
          "alternateName": null,
          "description": null,
          "name": null,
          "url": null
        },
        "telephone": null,
        "alternateName": null,
        "description": null,
        "name": null,
        "url": null
      },
      "location": "Orlando, FL",
      "maximumSalary": null,
      "minimumSalary": null,
      "name": "Manager Trainee",
      "occupationalCategory": null,
      "qualifications": null,
      "query": "Retail Sales Manager",
      "responsibilities": null,
      "salaryCurrency": null,
      "skills": null,
      "source": "Indeed",
      "sourceId": "c35c3c7a5d61857e",
      "specialCommitments": null,
      "startDate": null,
      "title": "Manager Trainee",
      "url": "http://www.indeed.com/viewjob?jk=c35c3c7a5d61857e&qd=0YhWF1ggXeR_D_AC4ekfOruTBpHhozBGDIfLHBLnubD-2-W0u32WFrU39zSxqydN3J-4nOSXPQlGVSMv10v9koBwCaytx9cwv0CF6SqbAQokt0LCVy_rQinuMfW47e_m&indpubnum=3806336598146294&atk=1bvvn25klav8vcas",
      "workHours": null,
      "_terms": [
        "354994470"
      ],
      "lastObservedAt": 1511819124,
      "firstObservedAt": 1511819124,
      "objectID": "49116121"
    }
```

The advantage to using Algolia is that the jobs can be very quickly accessed. You can configure your own indexes to make sure the data fields you need to search are front and center. The downside to Algolia is the cost as their minimum package price is around $60 per month.

## Archiving jobs

Since most users don't need jobs that are stale and I wanted to minimize my Algolia costs, I decided to archive jobs older than 30 days by saving them to Amazon S3. These collections are just JSON files, so they could be re-imported into Algolia via their web interface or API at any time. The archival command is configurable to run any number of days back that you'd like.

## Setting up the project

I've been running the project in Docker, and have documented it [in the repository on Github](https://github.com/jobapis/collector). I welcome any additional input for documentation or support in the [Github issues](https://github.com/jobapis/collector/issues), but my time to update them will likely be limited going forward.
