# DataMade Site Launch Checklist
A checklist of miscellaneous tasks to do before launching a public website. 

## Usage
Make a new GitHub issue in your project called "Final Checklist" and copy/paste the following:


```
from the [DataMade Site Launch Checklist](https://github.com/datamade/site-launch-checklist)

## Framing / Call to Action
- [ ] Make sure that the site has a clear call to action. This should not be 'hey look at this cool tool'. Rather, it should be a way for someone to engage in a meaningful way on the issue being presented.

Some examples:

* Join a mailing list (which means you need to create one)
* Attend an event
* Share on Facebook/Twitter
* Donate to a particular organization
* Create a Tumblr for people to share interesting findings (if it's a data access site)

## Web Search Indexing
* [ ] If you have a staging site, tell the search engine robots not to index you with a robots.txt
* [ ] Make sure you allow indexing when you are ready to launch
* [ ] Make sure you handle the www subdomain with DNS redirect

## Google Analytics

* [ ] Create [Google Analytics](http://www.google.com/analytics/) account
* [ ] Hook up the GA Tracking Code (typically in our `analytics_lib.js` file)
* [ ] Set up relevant Goals and Funnels
* [ ] Set up [Google Webmaster Tools](https://www.google.com/webmasters/tools/home?hl=en)
* [ ] Verify site in Webmaster Tools with DNS TXT record
* [ ] Link Webmaster Tools to Google Analytics

## Sharing & Rich Snippets

- [ ] Set up general meta tags
 * `<meta name="description">`
 * `<meta name="author">`
- [ ] Set up Facebook meta tags & validate [here](https://developers.facebook.com/tools/debug/)
 * `<meta property="og:site_name">`
 * `<meta property="og:title">`
 * `<meta property="og:type">`
 * `<meta property="og:description">`
 * `<meta property="og:url">`
 * `<meta property="og:image">`
- [ ] Set up Twitter meta tags & validate [here](https://cards-dev.twitter.com/validator)
 * `<meta name="twitter:card">`
 * `<meta name="twitter:site">`
 * `<meta name="twitter:creator">`
 * `<meta name="twitter:description">` (note that this needs to be under 200 characters)
 * `<meta name="twitter:title">`
 * `<meta name="twitter:url">`
 * `<meta name="twitter:image:src">`
- [ ] Create 2-5 meme images using [Canva](http://canva.com/) or a similar tool

## Mobile Friendliness

Test on various mobile devices:
- [ ] scrolling is easy
- [ ] nav bar works
- [ ] hoverable things are tappable
- [ ] charts/maps look ok

## Printer Friendliness

Dynamic sizing, dark backgrounds, and interactivity don't play well with printers. 

Pick one: 
- [ ] Make a print stylesheet using a `@media print {}` media query, then add it to your site with `<link rel="stylesheet" type="text/css" href="css/print.css" media="print">`
- or -
- [ ] Use Firefox dev tools to remove offending elements (like sticky footers), alter colors where needed, and screenshot the entire page (here's how: https://stackoverflow.com/a/14830242).
- [ ] Slice the resulting PNG into a multi-page PDF by copy/pasting page-sized chunks into the rich text editor of your choice, i.e. Microsoft Word or Google Docs. Export it to PDF and add it to the directory your images are stored in.
- [ ] Add a link to the printer-friendly version to your website.

## Page Speed
- [ ] run the site through https://developers.google.com/speed/pagespeed/insights/

## Miscellaneous Polish
- [ ] add favicons, apple touch icons (http://www.favicomatic.com/)
- [ ] add 404 & 500 error pages
- [ ] setup HTTPS with [Let's Encrypt](https://letsencrypt.org/) or some other means.

## Load Testing

If your site relies on a database or server-side code, it should use caching and be load tested. If it's a static HTML or Jekyll site, you can skip this section.

- [ ] set up page [caching](https://en.wikipedia.org/wiki/Web_cache)
- [ ] write a script to load test all your pages. [Here's a good example from Illinois Sunshine](https://github.com/datamade/illinois-sunshine/blob/master/cache_builder.py)

## Testing

- [ ] Plan for a day of bugfixing. This day should happen after you have added the last features you plan on adding.

## GitHub Readme

If the site is open source, make sure the Readme.md is complete and accurate. 

Here's a few good examples:

- [Geomancer](https://github.com/associatedpress/geomancer/blob/master/README.md)
- [Illinois Sunshine](https://github.com/datamade/illinois-sunshine/blob/master/README.md)

The Readme should have the following sections:

- [ ] Overview
- [ ] Setup
- [ ] Running locally
- [ ] Team
- [ ] Errors / Bugs 
- [ ] Pull Requests
- [ ] Copyright and License

## Outreach

- [ ] Write up press release
- [ ] Identify who will be the primary person of contact and make their info prominent on the website and all PR
- [ ] Identify relevant media contacts to email
- [ ] Identify relevant social news sites (reddit, listservs, slack channels)
- [ ] Divide & conquer - send out the media blitz!
```

## Suggestions? 

We'd love to hear 'em. [Open an issue](https://github.com/datamade/site-launch-checklist/issues), or fork this repo and make it your own! 

## Copyright and Attribution

Copyright (c) 2016 DataMade. Released under [MIT License](https://github.com/datamade/site-launch-checklist/blob/master/LICENSE).
