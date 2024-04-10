# elitemastereric.github.io

# Links
- https://twitter.com/EliteMasterEric
- https://github.com/EliteMasterEric
- https://EliteMasterEric.newgrounds.com/
- https://www.youtube.com/@EliteMasterEric
- https://www.twitch.tv/EliteMasterEric
- https://stackoverflow.com/users/5583560/elitemastereric
- https://www.linkedin.com/in/eric-myllyoja-287876121/
- mailto:elitemastereric@gmail.com

## To-Do List
[X] Port all old blog posts
[X] Port all old blog post images
[X] Fix iframes
[X] Find a good site style
[X] Implement image zooming: https://github.com/adityatelange/hugo-PaperMod/issues/384#issuecomment-899219940
[] Reimplement tags
[] Readd footer image
[] Add links to footer
[] Implement table of contents and anchor links on headers
[] Add gisqus for comments

## Build Instructions

- Download Hugo and put it in `./lib/`
- Update `.vscode/settings.json` to add Hugo to the path
- Open VSCode terminal and run commands:
    - `hugo server` to preview on a local server, with hot reloading
    - `hugo server --buildDrafts` to include draft posts in preview
    - `hugo` to build a static site into `/public/`

## Notes
- Shortcodes: `{{<myshortcode Parameter>}}Content{{</myshortcode>}}` displays the shortcode content.
    - Parameters follow the name, and may be named, positional, or both (you can't mix in one call)
    - Use `%%` to fully render the contents.
    - Use `<>` to disable further rendering.
- Images included alongside an `index.md` are page resources.
- Pages are marked with "front matter":
    - `title` is the heading of the post.
    - `date` indicates the date displayed on a post, usually creation date. Future posts are not included. 
    - `draft` indicates a page is a work-in-progress and should not be included in public builds.
        - Draft pages are only included with the `--buildDrafts` flag.
    - `publishDate` indicates the date a page should be made live.
        - Future pages are only included with the `--buildFuture` flag.
    - `expiryDate` indicates the date a post should no longer be live.
        - Expired pages are only included with the `--buildExpired` flag.
    - `lastmod` indicates the date a post was last modified.
    
    - `layout` indicates a template name to use for the page. Exclude the extension.
    - `markup` indicates the content format to use: https://gohugo.io/content-management/formats/
        - `adoc`, `html`, `md`, `org`, `pdc`, or `rst`

    - `summary` provides a teaser of the content on the page, displayed on the blog listing.
    - `description` provides a summary of the page content, used in the page `<meta>`.
    - `keywords` provides a list of key words used in the page `<meta>`.
    - `weight`: Used to order pages in a collection, lighter items move to the top and heavier ones move to the bottom.

    - `aliases` provides a list of URLs that will redirect here.
    - `build`: Build options
    - `cascade`: A map of front matter keys passed down to any page's descendents.
    - `[params]`: A map of custom parameters
- Built-in shortcodes:
    - `figure` for including a caption with a photo
    - `gist` to embed a Github Gist.
    - `highlight` to embed a code snippet for a given language. Options: https://gohugo.io/functions/transform/highlight/
    - `instagram`
    - `param` uses a parameter from the front matter.
    - `ref` returns an absolute permalink for the page reference
    - `relref` returns a relative permalink
    - `twitter` or `tweet` displays a Twitter post.
    - `vimeo` with video id
    - `youtube` with video id
- Use emoji shortcodes: https://gohugo.io/quick-reference/emojis/