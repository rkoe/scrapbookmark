# Scrapbookmark
Scrapbook for Firefox Quantum (and probably Chromium), integrated into the browser bookmarks.

"Scrapbooking" websites (=storing websites incl. their meta-information and their current state; and managing them like bookmarks) in a browser is very useful. Unfortunately, the old Scrapbook addons (e.g. https://github.com/danny0838/firefox-scrapbook) for Firefox unfortunately do not work anymore with Firefox Quantum, and there's currently no working replacement
(except https://github.com/danny0838/webscrapbook, but this works quite differently than Scrapbook X and is unfortunately much harder to use).

So, here a Scrapbook for Firefox Quantum (and maybe also Chromium) -- based on bookmarks -- is developed.

## Current state
Working:
- Prototype, completely based on bookmarklets (instead of an addon) and a Python-script to convert/manage the scrapbooks
- read: open pages and meta-information/properties of old Scrapbooks with newer browsers:
  - convert the old meta-information to JSON-format by a Python script
  - create a scrapbook_bookmarks.html file, which includes the Scrapbook-hierarchy-tree and markers to distinguish stored pages from real bookmarks; this can be imported into the browser-bookmarks to access the Scrapbook-pages
  - read the meta-information/properties with a bookmarklet
- load source URL (by a bookmarklet)

- folders: create, rename, delete, reorder, sort, open all in tabs by the bookmarking-functionality of the browser
- hierarchy: reorder the pages/folders, remove entries etc. by the bookmarking-functionality of the browser
- multi-scrapbooks (all in the same bookmark-sidebar, but page-data stored in different directories)
- saving (work-in-progress):
  - store a page incl. its currently entered form-values
  - store eBay-pages with the end-timestamp prepended to the title, so sorting the bookmarks shows the next ending offers first
  - but: currently limited functionality
  
Limitations:
- deleting a page only deletes the entry in the bookmark, but not the page-data
- for saving pages:
  - an external Python-script, used as mime-handler, is necessary
  - several clicks and keystrokes are currently necessary to save a page and create the bookmark-entry
  - CSP: CSP may have to be disabled to save pages, since Firefox currently forbids bookmarklets to run if the page uses a CSP-policy, but Firefox is working on this (see Firefox-Bug: https://bugzilla.mozilla.org/show_bug.cgi?id=1478037)
  - XHR: XHR has to be enabled to save pages
- currently limited functionality

## Roadmap
- make the prototype work correctly and test it
- publish the code
- edit pages with the WebDeveloper tools and store the changes
- extend functionality (edit metadata, edit page, export, move pages to other scrapbooks, remove unused files, ...)
- convert a WebExtensions-addon to overcome the limitations above
