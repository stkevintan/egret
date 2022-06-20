---
{"dg-publish":true,"permalink":"/msal/auth/","dgHomeLink":true,"dgPassFrontmatter":false}
---


Actually I figured this out by myself.

The Manifest property seems to get ignored if you pass your Tenant-ID along the URL `https://login.microsoftonline.com/{tenant}/oauth2/v2.0/authorize`....

In the docs I found, that for both Business and Personal Account you have to pass `'common'` as `{tenant}`. `https://login.microsoftonline.com/common/oauth2/v2.0/authorize`

> The {tenant} value in the path of the request can be used to control who can sign into the application. The allowed values are
> 
> -   `common` for both Microsoft accounts and work or school accounts,
> -   `organizations` for work or school accounts only,
> -   `consumers` for Microsoft accounts only, and tenant identifiers such as the tenant ID or domain name.
