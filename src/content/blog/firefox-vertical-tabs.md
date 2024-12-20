---
title: 'Set Up Vertical Tabs in Firefox'
description: 'The basic process for replacing the horizontal tabs in Firefox with verticals ones.'
pubDate: 'Sep 13, 2024'
heroImage: '/blog-placeholder-3.jpg'
---

This is the process for use sidebery for a vertical tab bar, and completely hide the default horizontal tab bar.

1. Install the [Sidebery](https://addons.mozilla.org/en-US/firefox/addon/sidebery) extension
2. Go to `about:support`
3. Open the profile directory
4. Create a `chrome` directory
5. Create a `userChrome.css` file in that directory
6. Add the following
   ```
   #TabsToolbar { visibility: collapse !important; }
   ```
7. Go to `about:config`
8. Set `toolkit.legacyUserProfileCustomizations.stylesheets` to `true`
9. Restart FireFox
10. Right click on the toolbar and click "Customize Toolbar"
11. In the bottom-left corner, enable "Title Bar"
12. Click "Done" in the bottom-right corner.
