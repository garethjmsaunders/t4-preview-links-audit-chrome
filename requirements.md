Act as an expert in writing extensions for the Chrome browser on Windows 11.

I need a Chrome extension to help me with a local project, so I will be sideloading the extension locally and not needing to upload it to the Chrome Web Store.

I'd like to talk through my requirements with you first before you write any code for me.

Here is the problem I am trying to solve:

* I need to audit web pages created in our enterprise content management system, Terminalfour (T4).

* I want to use the plugin while viewing the pages generated using the T4 preview.

* When I click the extension button on my Chrome toolbar, I want the extension to scan the contents of the preview page (everything within the element <main id="content-begins">) and highlight all links that it finds.

* There are 3 categories of links:

1. St Andrews links
Description: Links to other pages on the University of St Andrews website.
Reason: We have two T4 instances (T4 New and T4 Old). Any St Andrews links in preview indicate that these are pages contained in T4 Old and will need to be updated soon as T4 Old is being decommissioned.)
Links begin with: https://www.st-andrews.ac.uk/ or another subdomain on st-andrews.ac.uk that isn't t4live (below)
Highlight colour: background #00aeef; text colour: black

2. T4 links
Description: Links that have T4 URLs which on publish will be converted to St Andrews URLs.
Reason: These are links to other pages in T4 New and do not need to be updated.
Links begin with: https://t4live.st-andrews.ac.uk/terminalfour/preview/
Highlight colour: background #c60c46; text colour white

3. External links
Description: Links to webpages outside the St Andrews domain
Reason: This will help us to identify pages that need an external links disclaimer at the foot of the main content.
Links begin with: Anything that does not have a st-andrews.ac.uk domain.

* I would also like these 3 categories of links to be output somewhere so I can copy and paste them into an audit document. I am thinking that outputting these to the browser console sounds like a good idea.

* I would like these links to be output in alphabetical order under the category headings showing the link text and the link URL. For example:

# St Andrews links

Current students
https://www.st-andrews.ac.uk/students/

Staff
https://www.st-andrews.ac.uk/staff/

# T4 links

Access to work
https://t4live.st-andrews.ac.uk/terminalfour/preview/2/en/44230

British Sign Language (BSL)
https://t4live.st-andrews.ac.uk/terminalfour/preview/2/en/47969

# External links

Google
https://www.google.co.uk/

* I will need an icon for the plugin. I can provide this but I will need you to tell me what dimensions and format I need.

This is my thinking so far. 

Does this all make sense to you?

Does it look feasible?

Is there anything else that you think would be useful to specify in the requirements? Have I missed anything?

---

Answers to your questions:

1. External link highlighting
background #ffdf00; colour: black

2. Duplicate links
Excellent point. If there are any duplicates, please mark the number of duplicates in parentheses after the link text in the console output. For example:

Access to work (2)
https://t4live.st-andrews.ac.uk/terminalfour/preview/2/en/44230

3. Relative links
There are unlikely to be any relative links -- there certainly should not be. But this is an excellent point. I would like you to highlight any relative links with:
background: #111111; color: white;

4. Link text fallback
Yes. If a link has no visible text (e.g. it's an image or empty), still log the URL and use something like [no text].

5. Performance
There may be a few pages that are very long. But these will be the exception.

6. Copy/paste helper
An optional feature that outputs the same categorised list in a pop-up UI (e.g. a text box you can copy from) instead of only in the console sounds very helpful. Yes please.