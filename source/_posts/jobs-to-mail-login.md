---
title: JobsToMail User Login and Filtering Recruiter Listings
date: 2016-11-01 21:01:56
tags:
- releases 
- announcements
- jobs-to-mail
---

Tonight we released a basic token-based user login functionality on [JobsToMail](https://www.jobstomail.com/) which allows users to log in and see their current searches as well as add new ones to their user account. We also released our first premium feature that allows users to filter out recruiters. This feature is currently only open to users who request access by emailing [upgrade@jobstomail.com](mailto:upgrade@jobstomail.com).

Both of thesse features are among several that will go into the [version 1.0 release of JobsToMail](https://github.com/jobapis/jobs-to-mail/milestone/1) expected sometime in the beginning of 2017. More details on each feature are below.

## Token-based user login

Token-based logins (also known as "passwordless" logins) have trade-offs. On one hand, they can be more secure and help ensure that users don't share accounts or use weak passwords. On the other hand, they are slightly more difficult to use, although that point is arguable. With passwordless logins, a user does not have to remember or type a password, but she does have to have access to her email address. [Here's a good blog post on the reasons for going passwordless](http://notes.xoxco.com/post/27999787765/is-it-time-for-password-less-login).

### How it works

The basic flow for our token-based login is as follows:

#### 1. Click `Login` and enter email

![Login with email](/images/email.png)

#### 2. Check email account for the token

It may take a few seconds for the email to reach you.

#### 3. Enter your token OR click the link in the email

![Login with email](/images/token.png)

#### 4. You will be immediately logged in

![Login with email](/images/logged-in.png)

### Notes about token-based login on JobsToMail.com

- Our tokens expire in 7 days. If you don't use the token by that time you will have to generate a new one to log in.
- Tokens are only good for **one time use**. This means you can't share your token with others.
- Tokens use the same construct as the confirmation links we send when new users sign up. This means that new users when confirmed are automatically logged in so they can explore their searches immediately.
- If you have any issues, feel free to report them on [github](https://github.com/jobapis/jobs-to-mail/issues) or [email me directly](mailto:khughes.me@gmail.com).

## Filtering recruiter posts

This feature has been requested by several of our users who are recruiters, but it takes more work to maintain than the basic functionality of JobsToMail. We are still building a list of recruiting firms and improving the filtering mechanism, so expect this feature to improve greatly, and we're looking for testers in new locations.

If you'd like to try out the recruiter filter, please email [upgrade@jobstomail.com](mailto:upgrade@jobstomail.com).
