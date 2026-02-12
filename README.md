# 🚀 DataMade Site Launch Checklist
_A checklist of tasks to do before launching a public website._

## Usage
Launch preparation generally takes a day or more. You should also reserve a day for bugfixing after you have wrapped the last feature. Be sure to plan accordingly!

Once you're ready, make a new GitHub issue in your project called "Launch Checklist" and copy/paste the following:

```
From the [DataMade Site Launch Checklist](https://github.com/datamade/site-launch-checklist)

## Load Testing and Website Optimization

If your site relies on a database or server-side code, you should load test and optimize the site for the level of traffic you anticipate. If you're launching a static site, you can skip this section.

* [ ] Set up [caching](https://docs.djangoproject.com/en/stable/topics/cache/)
* [ ] Run the site through [Google Lighthouse](https://developers.google.com/web/tools/lighthouse/)
* [ ] Write a script to load test your site
    - We like [Locust](https://docs.locust.io/en/stable/) for this. See [LA Metro Councilmatic](https://github.com/datamade/la-metro-councilmatic#load-testing) for a basic example.

If you're writing a Django application, [Django Debug Toolbar](https://django-debug-toolbar.readthedocs.io/en/latest/) is a great tool for identifying duplicated and/or sluggish queries.

## Deployment and DNS

* [ ] Create a production deployment
* [ ] Double check that production-level resources have been provisioned
* [ ] Purchase your domain and create the DNS record to point it at your production deployment
* [ ] If you are using [Cloudflare](https://www.cloudflare.com/) (you should!), set up the domain to point to the Cloudflare nameservers and configure the DNS records on Cloudflare
* [ ] Set up SSL if needed (on services like Heroku and Netlify, this will be automatic)

## Web Search Indexing

* [ ] Create a [robots.txt](https://developer.mozilla.org/en-US/docs/Glossary/Robots.txt) file that disallows indexing of your staging site and allow indexing of your production site
* [ ] Create a [sitemap.xml](https://en.wikipedia.org/wiki/Sitemaps) that lists all pages on your site that you want indexed
* [ ] If using a root domain for your URL, set DNS records to redirect the www subdomain to your root domain
* [ ] Set up [Google Search Console](https://search.google.com/search-console) and verify the site and optionally submit your sitemap

## Tracking Site Traffic and Analytics

If you are using Cloudflare, you will get their [Web Analytics](https://www.cloudflare.com/web-analytics/) as part of that service.

* [ ] Optionally, create a [Google Analytics](https://analytics.google.com/) account and add the javascript code to your site

## Accessibility

* [ ] Overview - test all pages with a tool like [Axe DevTools](https://chrome.google.com/webstore/detail/axe-devtools-web-accessib/lhdoppojpmngadmnindnejefpokejbdd) or [Google Lighthouse](https://developers.google.com/web/tools/lighthouse/)
* [ ] Keyboard - confirm all functionality works with a keyboard _only_. This includes logical focus order (typically left-right top-down) and no focus traps (except modals)
* [ ] Screen Reader - test pages with a screen reader like [NVDA](https://www.nvaccess.org/download/) on Windows or [VoiceOver on Mac](https://support.apple.com/guide/voiceover/turn-voiceover-on-or-off-vo2682/mac), confirming that all content is clear, including:
  * [ ] Confirm no repeat or unclear button titles (e.g. "Click here" or "View more")
  * [ ] Confirm images have proper alt tags for their context (including `alt=""` for decorative images)
* [ ] Structure - Using [Accessibility Insights for Web](https://chrome.google.com/webstore/detail/accessibility-insights-fo/pbjjkligggfmakdaogkfomddhfmpjeni) or another tool, confirm all pages have clear and sufficient heading levels. Keep in mind it should act like a table of contents, you want to have enough headings to be useful but not one for every paragraph.
* [ ] Color Blindness - make sure no information is conveyed via color only, potentially by testing using grayscale mode in [Accessibility Insights for Web](https://chrome.google.com/webstore/detail/accessibility-insights-fo/pbjjkligggfmakdaogkfomddhfmpjeni)

## Sharing & Rich Snippets

* [ ] Create a share card using [Canva](http://canva.com/) or a similar tool
* [ ] Set up general meta tags
    ```html
    <meta name="description" content="${SITE_NAME}" />
    <meta name="author" content="${SITE_AUTHOR}" />
    ```
* [ ] Set up Facebook meta tags & validate [here](https://developers.facebook.com/tools/debug/)
    ```html
    <meta property="og:type" content="website">
    <meta property="og:site_name" content="${SITE_NAME}">
    <meta property="og:description" content="${SITE_DESCRIPTION}">
    <meta property="og:image" content="${SHARE_CARD_URL}">
    <meta property="og:title" content="${PAGE_TITLE}">
    <meta property="og:url" content="${PAGE_URL}">
    ```

Confirm your meta tags work by checking on [https://metatags.io](metatags.io)

## Miscellaneous Polish

* [ ] Add favicons and Apple touch icons (http://www.favicomatic.com/)
* [ ] Add custom 404 & 500 error pages

## Browser and mobile compatibility

* [ ] Use BrowserStack to confirm that your site is compatible with the browsers you wish to support

Using BrowserStack's mobile device emulators and/or your own mobile device, confirm that:

* [ ] Scrolling is easy
* [ ] Nav bar works
* [ ] Hoverable things are tappable
* [ ] Charts and maps look ok

## Printer Friendliness

Dynamic sizing, dark backgrounds, and interactivity don't play well with printers.

Pick one:

* [ ] Make a print stylesheet using a `@media print {}` media query, then add it to your site with `<link rel="stylesheet" type="text/css" href="css/print.css" media="print">`

- or -

* [ ] Use your browser's dev tools to remove offending elements (like sticky footers), alter colors where needed, and [screenshot the entire page](https://stackoverflow.com/a/14830242).
* [ ] Add a link to the printer-friendly version to your website.

## GitHub README

If the site is open source, make sure the README.md is complete and accurate.

Here's a few good examples:

- [LA Metro Councilmatic](https://github.com/datamade/la-metro-councilmatic)
- [Parserator]([https://github.com/datamade/illinois-sunshine/blob/master/README.md](https://github.com/datamade/usaddress/blob/main/README.md))

The README should generally contain information on the following:

* [ ] Project overview
* [ ] System-level dependencies
* [ ] Running locally
* [ ] Bug reports and contributing
* [ ] Copyright and license
```

## Suggestions?

We'd love to hear 'em. [Open an issue](https://github.com/datamade/site-launch-checklist/issues), or fork this repo and make it your own!

## Copyright and Attribution

Copyright (c) 2026 DataMade. Released under [MIT License](https://github.com/datamade/site-launch-checklist/blob/master/LICENSE).
