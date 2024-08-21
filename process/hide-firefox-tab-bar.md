1. Go to `about:support`
2. Open the profile directory
3. Create a `chrome` directory
4. Create a `userChrome.css` file in that directory
5. Add the following
```
#TabsToolbar { visibility: collapse !important; }
```
6. Go to `about:config`
7. Set `toolkit.legacyUserProfileCustomizations.stylesheets` to `true`
