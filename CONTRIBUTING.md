#How to Contribute

In a nutshell, follow the workflow, and write tested, quality code.
Getting 'it' out the door at any cost is not the idea.
You can still ship fast and often doing things properly.

##Commits

* Commits must be small and make sense when viewed in isolation. Your commit message
 must also make sense. The title should be short and be prefixed with the
 Bundle or section it affects, the body holds the full explanation of the change
 Which again will be fairly short, as your commit is small, sometimes, you won't even need
 a body of the commit message.

###Examples of bad commit messages are

 * Fixes Bugs
 * Changes view because John wanted it this way
 * Minifies file

###Examples of good commit messages are

 * [ActonGardens] Adds bootstrap CSS files
 * [config, security] Disabled security for login area
 * [ActonGardens][Templates][Partials] Calls Controllers error response now using JS
     * The response format of the calls controller when erroring, is now JavaScript
      This is executed by the browser and updates the view rather than having
      the view poll for a response, this is much more efficient


###Auto Closing an Issue

Your commit message should close *one* issue. This is done by using certain words
 followed by a hash and the issue ID like this. Closes #123
If that was your commit body, you will auto close issue 123 when your PR is merged
and the commit and issue will be linked together.
This helps when looking back over issues and the revision history.

If there is no issue, you may be making changes based on a basecamp task.
If that is the case, then please paste the link to the todo item in your comment.

##Pull Requests

* All changes must be done in a topic branch on your fork of the project in
 the form of a Pull Request (PR)
* All PRs should be small, and include only one change, this makes them easier to
 review, easier for you to write, and easier to document & test

1) Fork the repo.

2) Make the changes required

3) Push to your fork and submit a pull request.

##Getting your PR accepted

Some things that will increase the chance that your pull request is accepted.

* Give your PR a meaningful title for the change, and ensure the description
 is complete and covers what you are doing, and potentially why if relevant.

* Use PSR Coding Standards and Style Guides

    https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-0.md
    https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-1-basic-coding-standard.md
    https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md


* Update the documentation, examples elsewhere, guides,
  whatever is affected by your contribution

Failure to comply with these requirements, will result in your PR not being merged.
However the PR process is iterative, so you don't need to get it right first time,
we will review, comment and iterate on the solution until it's ready to be merged.
The important thing is not to find the quickest solution, but to find the best solution; Reusable, solid, testable, simple.

##BRADLEY DYER CODING STANDARDS AND GUIDELINES

## A guide to the default HTML

### Writing valid code

Valid code is code that meets the W3C's standards. You can check your code at any time using the [W3C validator](http://validator.w3.org/).

It is important that you understand how browsers work - this will allow you to understand the ‘why’ of best practice. We encourage you to watch this [video](http://www.youtube.com/watch?v=Lsg84NtJbmI).

### Writing well formed code

Well formed code is neat, correctly aligned and indented. Comment your code as required.

### Writing semantically correct HTML

To write semantically correct HTML, you need to select the correct HTML element to mark-up the content. In other words, this means using a `<table>` to mark-up tabulated content, using a `<ul>` to mark-up an unordered list, and so on.

                        <pre>&lt;ul&gt;
  &lt;li&gt;Apples&lt;/li&gt;
  &lt;li&gt;Oranges&lt;/li&gt;
  &lt;li&gt;Pears&lt;/li&gt;
  &lt;li&gt;Peaches&lt;/li&gt;
&lt;/u&gt;
Not:
&lt;p&gt;Apples&lt;br&gt;Oranges&lt;br&gt;Pears&lt;br&gt;Peaches&lt;/p&gt;</pre>

Semantically correct HTML is instrumental in creating SEO compliant and accessible web pages.

### Progressive enhancement

In practical terms, it’s easiest to break the concept of progressive enhancement into different layers, each one building on the previous to improve the experience of interacting with the website.

The first layer is clean, semantic HTML. This allows text-based, speech-based, antiquated and robotic user-agents to navigate the content of your website properly.

The second layer is CSS. This allows visual-based user-agents to display or alter the visual representation of your website’s content.

The third layer is JavaScript. This allows user-agents that are capable of using it to provide your users with enhanced usability.

### Naming conventions

`html` and `php` page names should be _all lowercase_ and _hyphenated_.

                        <pre>search-results.html</pre>

Your css classes and id's should be logically named.

                        <pre>.user-error{background:red;}
 not
.red-box{background:red;}</pre>

ID's should be unique and used once only per page.

Images should be logically named using hyphens between words.

                        <pre>mr-john-smith-ceo-galliard.jpg</pre>

When creating a number of images for the same use, consider naming them by what they are, followed by a unique identifier.

                        <pre>developments-slider-st-johns.jpg
developments-slider-st-venns.jpg
developments-slider-st-thomas.jpg</pre>

### Conditional `html` classes

A series of IE conditional comments apply the relevant IE-specific classes to
                        the `html` tag. This provides one method of specifying CSS fixes for specific
                        legacy versions of IE.

When using the conditional classes technique, applying classes to the `html`
                        element has several benefits:

*   It avoids a [file blocking issue](http://webforscher.wordpress.com/2010/05/20/ie-6-slowing-down-ie-8/) discovered by Stoyan Stefanov and Markus Leptien.
*   It avoids the need for an empty comment that also fixes the above issue.
*   It can improve the clarity of code in multi-developer teams.

After implimenting the conditional comments, you can target Internet Explorer browsers in your css as follows:

                        <pre>footer {color:#505050;}
.lt-ie7 footer {color:#333;}  /* ie6 */
.ie7 footer {color:#000;}     /* ie7 */
.ie8 footer {color:#fff;}     /* ie8 */
.ie9 footer {color:#aaa;}     /* ie9 */</pre>

### The `no-js` class

Allows you to target browsers with JavaScript disabled (`.no-js`) or enabled (`.js`).

After implimenting the conditional comments, you can target browsers with javaScrip enabled/disabled in your css as follows:

                        <pre>.js footer {color:#000;}      /* javaScript enabled */
.no-js footer {color:#fff;}   /* javaScript disabled */</pre>

More here: [Avoiding the FOUC](http://paulirish.com/2009/avoiding-the-fouc-v3/).

### The order of meta tags, and `<title>`

As recommended by [the HTML5 spec](http://www.whatwg.org/specs/web-apps/current-work/complete/semantics.html#charset)
                        (4.2.5.5 Specifying the document's character encoding), add your charset declaration early (before any ASCII art ;) to avoid a potential [encoding-related security issue](http://code.google.com/p/doctype-mirror/wiki/ArticleUtf7) in IE. It should come in the first [1024 bytes](http://www.whatwg.org/specs/web-apps/current-work/multipage/semantics.html#charset).

The charset should also come before the `<title>` tag, due to [potential XSS vectors](http://code.google.com/p/doctype-mirror/wiki/ArticleUtf7).

### X-UA-Compatible

This makes sure the latest version of IE is used in versions of IE that contain multiple rendering engines. Even if a site visitor is using IE8 or IE9, it's possible that they're not using the latest rendering engine their browser contains. To fix this, we use:

                        <pre><span class="nt">&lt;meta</span> <span class="na">http-equiv=</span><span class="s">"X-UA-Compatible"</span> <span class="na">content=</span><span class="s">"IE=edge"</span><span class="nt">&gt;</span></pre>

The `meta` tag tells the IE rendering engine it should use the latest, or edge, version of the IE rendering environment.

This `meta` tag ensures that anyone browsing your site in IE is treated to the best possible user experience that their browser can offer.

This line breaks validation. To avoid this edge case issue it is recommended that you **remove this line and use the `.htaccess`** (or other server config)
                        to send these headers instead. You also might want to read [Validating:
                        X-UA-Compatible](http://groups.google.com/group/html5boilerplate/browse_thread/thread/6d1b6b152aca8ed2).

If you are serving your site on a non-standard port, you will need to set this header on the server-side. This is because the IE preference option 'Display intranet sites in Compatibility View' is checked by default.

### Mobile viewport

There are a few different options that you can use with the [`viewport` meta tag](https://docs.google.com/present/view?id=dkx3qtm_22dxsrgcf4 "Viewport and Media Queries - The Complete Idiot"). You can find out more in [the Apple developer docs](http://j.mp/mobileviewport). 

                        <pre><span class="nt">&lt;meta</span> <span class="na">name=</span><span class="s">"viewport"</span> <span class="na">content=</span><span class="s">"width=device-width, initial-scale=1"</span><span class="nt">&gt;</span></pre>

### Favicons and Touch Icon

The shortcut icons should be put in the root directory of your site. This standard project provides a **default set of icons** (including a favicon and  Apple Touch Icons) that you can use as a baseline to create your own. It can be found at _path-to-template_

### Modernizr

[Modernizr](http://modernizr.com) is a JavaScript library which adds classes to the `html` element based on the results of feature testing. Modernizr also ensures that all browsers can make use of HTML5 elements (as it includes the HTML5 Shiv). This allows you to target parts of your CSS and JavaScript based on the features supported by a browser.

For example, for browsers that don't support multiple background images, you could write fallback CSS as follows to specify a different background image:

                        <pre>.intro-wrapper{
  background:url(img_tree.gif),url(img_flwr.gif);
  background-size:100% 100%;
  background-repeat:no-repeat;
}
.no-multiplebgs .intro-wrapper{background:url(img_tree_and_flower.jpg) 0 0 no-repeat #333);}</pre>

In general, in order to keep page load times to a minimum, it's best to call any JavaScript at the end of the page because if a script is slow to load from an external server it may cause the whole page to hang. That said, the Modernizr script _needs_ to run _before_ the browser begins rendering the page, so that browsers lacking support for some of the new HTML5 elements are able to handle them properly. Therefore the Modernizr script is the only JavaScript file synchronously loaded at the top of the document.

### Upgrade Browser Prompt

The standard project `header include` includes a prompt to users of legacy browsers to upgrade their browser. The message will appear at the top of the page. It uses cookies (see main.js and plugins.js) to show the message once only per user session.

                        <pre>You are using an **outdated** browser. Please [upgrade your browser](http://browsehappy.com/) to improve your experience.<button aria-hidden="true" class="close" type="button">×</button></pre>

### Google CDN for jQuery

The Google CDN (Content Delivery Network) version of the jQuery JavaScript library is referenced towards the bottom of the page using a protocol-independent path. A local fallback of jQuery is included for rare instances when the CDN version might not be available, and to facilitate offline development.

Regardless of which JavaScript library you choose to use, it is well worth the time and effort to look up and reference the Google CDN version. Our users may already have this version cached in their browsers, and Google's CDN is likely to deliver the asset faster than our server.

### Google Analytics Tracking Code

Finally, an optimized version of the latest Google Analytics tracking code is included at the bottom of each html page.

    <script>
      (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
      (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
      m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
      })(window,document,'script','//www.google-analytics.com/analytics.js','ga');

      ga('create', 'UA-xxxxxxxx-x', 'website.com');
      ga('send', 'pageview');
    </script>

You will need to change UA-XXXXX-X to the client's site ID to configure their analytics.

More information:

*   [Optimizing the asynchronous Google Analytics
                            snippet](http://mathiasbynens.be/notes/async-analytics-snippet).
*   [Tracking Site Activity - Google Analytics](http://code.google.com/apis/analytics/docs/tracking/asyncTracking.html).

### Fonts

We use xxx and xxx for custom web fonts. Log in details are available in [keypass](http://keepass.info/)???

### Font Awsome

We use [font-awsome](http://fortawesome.github.io/Font-Awesome/) to display retina ready icons on our web sites. You can place Font Awesome icons just about anywhere with the `<i>` tag.

                        <pre>`<i class="fa fa-eur"></i>` renders 
`<i class="fa fa-scissors"></i>` renders 
`<i class="fa fa-angle-right"></i>` renders 
`<i class="fa fa-fast-forward"></i>` renders 
`<i class="fa fa-apple"></i>` renders 
`<i class="fa fa-volume-up"></i>` renders </pre>

[More examples ](http://fortawesome.github.io/Font-Awesome/examples/)

Designers that want to create their own icon set can follow [this tutorial](http://www.webdesignerdepot.com/2012/01/how-to-make-your-own-icon-webfont/).

## CSS

The standard project includes a handful of base styles in styles.css that you can build on.

Please comment all your CSS with an apropriate opening and closing comment, as well as additional comments within the opening / closing comment if required. This will help when maintaining the codebase down the line.

/* map-canvas ---------------------------------------------------------------- */

  #contact-map-canvas {
      height: 450px;
      margin: 0;
      padding: 0;
      border:1px solid #ccc;
  }
  /* contact-map-info-window */
  .contact-map-info-window{width:300px;}

/* map-canvas ---------------------------------------------------------- [END] */

styles.css includes Media Queries to build up your mobile styles for wider/narrower viewports bassed on the bootstrap3 breakpoints.

styles.css is well commented, but if you have any questions, just ask.

## JavaScript

We use [jQuery](http://api.jquery.com/). If you are unfamiliar with jQuery, a good place to start learning is the [jQuery learning center](http://learn.jquery.com/).

Our scripts are organised as follows:

### `main.js`

This file can be used to contain or reference your site/app JavaScript code. For larger projects, you can make use of a JavaScript module loader, like [Require.js](http://requirejs.org/), to load any other scripts you need to run.

### `plugins.js`

This file can be used to contain all your plugins, such as jQuery plugins and other 3rd party scripts.

Read more about [jQuery plugin authoring](http://docs.jquery.com/Plugins/Authoring#Getting_Started)

### Vendor

This directory can be used to contain all 3rd party library code such as bootstrap and polyfiller.

Minified versions of the latest jQuery and Modernizr libraries are included by default. You may wish to create your own  [custom Modernizr build](http://www.modernizr.com/download/).

## SEO considerations

An essential part of good web design and development is SEO. Valid, well-structured code is the key to ensuring that content is properly indexed by search engines.

### Be aware of SEO best practices

Read Google’s [SEO starter guide](http://static.googleusercontent.com/external_content/untrusted_dlcp/www.google.co.uk/en/uk/webmasters/docs/search-engine-optimization-starter-guide.pdf) and [developer guidelines](https://support.google.com/webmasters/answer/35769?hl=en&amp;topic=2370419&amp;ctx=topic).
You should also be aware of [image sitemaps](https://support.google.com/webmasters/answer/178636?hl=en) and follow Google’s [image publishing guidelines](https://support.google.com/webmasters/answer/114016?hl=en).

### Indexability

Use semantic Mark-up that's readable and logical when JavaScript and CSS are disabled (progressive enhancement). All page content must be in HTML; avoid iframes or JavaScript for loading initial indexable content.

All links should be to HTML destinations.

                        <pre>&lt;a href="/shelf/jordan/page/2"&gt;
Instead of:
&lt;a href="javascript:loadPage(2);"&gt;</pre>

This lets the page get indexed correctly by search engines and allows users to open the page in new tabs and windows.

### Optimisation

The title tag should feature target keywords for the unique page. The titles should be unique to each page. Headings (h1,h2,etc) should form an outline of the document and represent the most important keywords for that page. URLs should be human-readable with primary target keywords present in them:

                        <pre>http://domain.com/mens-shoes/basketball/jordan/jordan-mens-ajf-6-basketball-shoe/
vs
http://domain.com/ecomm.cfm?view=prod&amp;prodId=23425</pre>

### Sitemap

Consider adding a [sitemap](http://www.sitemaps.org/protocol.html) to compliment organic SEO.

### Schema

Use schema to add semantic meaning to mark-up. Read [SEO Benefits For Real Estate Companies Using Schema.org](http://blog.sharpeproperties.com/2012/03/seo-benefits-for-real-estate-companies.html)

More at [schema.org ](http://www.schema.org)

### Analytics

To set up a new analytics account for a client:

1.  Set up a GMAIL account using the following format:

        *   First Name: galliard
    *   Last Name: homes
    *   Email: galliardhomesltd@gmail.com
    *   Password: ghomes!!!
2.  Set up an analytics account:

        *   (same as Google Mail login)
    *   Email: galliardhomesltd@gmail.com
    *   Password: ghomes!!!
3.  Update the analytics tracking code on the client's site.

## Accessibility

As with SEO, valid, well-structured code is the key to ensuring that content is made accessible to those with limited web capabilities.

Web accessibility refers to the inclusive practice of making websites usable by people of all abilities and disabilities.

When sites are sympathetically designed, developed and edited, all users can have equal access to information and functionality. For example, when a site is coded with semantically meaningful HTML, with textual equivalents provided for images and with links named meaningfully, this helps blind users using text-to-speech software and/or text-to-Braille hardware.

When text and images are large and/or enlargeable, it is easier for users with poor sight to read and understand the content.

When links are underlined (or otherwise differentiated) as well as coloured, this ensures that colour blind users will be able to notice them.

When clickable links and areas are large, this helps users who cannot control a mouse with precision.

When pages are coded so that users can navigate by means of the keyboard alone, or a single switch access device alone, this helps users who cannot use a mouse or even a standard keyboard (Provide skip links).

When videos are closed captioned or a sign language version is available, deaf and hard-of-hearing users can understand the video.

When flashing effects are avoided or made optional, users prone to seizures caused by these effects are not put at risk. And when content is written in plain language and illustrated with instructional diagrams and animations, users with dyslexia and learning difficulties are better able to understand the content.

When sites are sympathetically built and maintained, all of these users can be accommodated without decreasing the usability of the site for non-disabled users.

All Bradley Dyer developers should be familiar with The W3C [checklist](http://www.w3.org/WAI/GL/2005/06/checklist-proto.html) of checkpoints for accessibility and strive to comply with them.

                        All Bradley Dyer developers should be familiar with the [WCAG Accessibility Guidelines](http://en.wikipedia.org/wiki/Web_Content_Accessibility_Guidelines)

                        For enterprise level web-builds, the completed template set _could_ be independently audited by an external body such as the [RNIB](http://www.rnib.org.uk/professionals/webaccessibility/services/siteaudits/Pages/site_audits.aspx).

Some nice articles and other accessibility resources can be found at [Web AIM](http://webaim.org/).

[Contrast Ratio Checker ](http://juicystudio.com/services/luminositycontrastratio.php)

## Cookie Compliance

If required, you could consider using [cookie control](http://www.civicuk.com/cookie-law/index), or [cookie concent](http://sitebeam.net/cookieconsent/).

## Testing

Test as you go, ensuring that your code is valid, well formed (neatly structured), well commented and [progressively enhanced](http://coding.smashingmagazine.com/2009/04/22/progressive-enhancement-what-it-is-and-how-to-use-it/) and meets our SEO and Accessibility standards. Also ensure that all components (sliders, calculaters, forms, maps, etc) work as expected.

Once you have finished writing the code base, you should perform a thorough cross browser / cross device check to ensure that there are no display issues.

If there's time, it's a good idea to have one of the other developers test your code for you.

Project managers should perform a final test to satisfy themselves that the clients brief has been met before showing the site to the client for sign off.

Some good stuff here... [The Ultimate Website Launch Checklist ](http://www.boxuk.com/upload/2014/02/Relaunched-Ultimate-Website-Checklist-2.0.pdf)


