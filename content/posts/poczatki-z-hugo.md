---
title: "Poczatki Z Hugo"
date: 2020-05-18T18:37:02+02:00
draft: true
---

Step 4: Add Some Content
You can manually create content files (for example as content/<CATEGORY>/<FILE>.<FORMAT>) and provide metadata in them, however you can use the new command to do few things for you (like add title and date):

hugo new posts/my-first-post.md

Edit the newly created content file if you want, it will start with something like this:

---

title: "My First Post"
date: 2019-03-26T08:47:11+01:00
draft: false

---

Step 5: Start the Hugo server
Now, start the Hugo server with drafts enabled:

▶ hugo server -D

                   | EN

+------------------+----+
Pages | 10
Paginator pages | 0
Non-page files | 0
Static files | 3
Processed images | 0
Aliases | 1
Sitemaps | 1
Cleaned | 0

Total in 11 ms
Watching for changes in /Users/bep/quickstart/{content,data,layouts,static,themes}
Watching for config changes in /Users/bep/quickstart/config.toml
Environment: "development"
Serving pages from memory
Running in Fast Render Mode. For full rebuilds on change: hugo server --disableFastRender
Web Server is available at http://localhost:1313/ (bind address 127.0.0.1)
Press Ctrl+C to stop
Navigate to your new site at http://localhost:1313/.

Feel free to edit or add new content and simply refresh in browser to see changes quickly (You might need to force refresh in webbrowser, something like Ctrl-R usually works).

Step 6: Customize the Theme
Your new site already looks great, but you will want to tweak it a little before you release it to the public.

Site Configuration
Open up config.toml in a text editor:

baseURL = "https://example.org/"
languageCode = "en-us"
title = "My New Hugo Site"
theme = "ananke"
Replace the title above with something more personal. Also, if you already have a domain ready, set the baseURL. Note that this value is not needed when running the local development server.

Tip: Make the changes to the site configuration or any other file in your site while the Hugo server is running, and you will see the changes in the browser right away, though you may need to clear your cache.

For theme specific configuration options, see the theme site.

For further theme customization, see Customize a Theme.

Step 7: Build static pages
It is simple. Just call:

hugo -D
Output will be in ./public/ directory by default (-d/--destination flag to change it, or set publishdir in the config file).

Drafts do not get deployed; once you finish a post, update the header of the post to say draft: false. More info here.

See Also
External Learning Resources
