Web content never expires. A blog post written in 2011 will live on in search
engine results for years.

[Rust](http://www.rust-lang.org/) has undergone a _lot_ of change over the last
few years, often in completely incompatible ways. This means the Internet is
littered with content and posts that were accurate at the time, but have since
been obsoleted.

To ensure old content gets properly flagged, with no effort needed by the
author, we've created a GitHub-driven badge service. See
[the user-friendly website](http://steveklabnik.github.io/rust-community-versions/)
for more details on the general idea.

## Updating a badge

Badges are stored as Jekyll posts. For example, the badge for this blog post:

* "Pointers in Rust: a Guide" [http://words.steveklabnik.com/pointers-in-rust-a-guide](http://words.steveklabnik.com/pointers-in-rust-a-guide)

Is stored at:

* [\_posts/2013-10-18-pointers-in-rust-a-guide.md](https://github.com/steveklabnik/rust-community-versions/blob/gh-pages/_posts/2013-10-18-pointers-in-rust-a-guide.md)

Versioning informations is store in the YAML front-matter of that post:

```
---
layout: post
url: http://words.steveklabnik.com/pointers-in-rust-a-guide
title: "Pointers in Rust: a Guide"
date: 2013-10-18
start_version: 0.8
---
```

To update the badge (as seen the blog post at words.steveklabnik.com), open a PR changing
the YAML front-matter.

## Creating a badge

To create and embed a badge, first author a Jekyll post with the version
information as exists. Most badges are likely to be for current content, and
thus may only have a `start_version` property.

To embed your badge, use the filename to determine the badge URL. For example
this filename:

```
_posts/2013-10-18-pointers-in-rust-a-guide.md
```

Is used as a badge with the following markup:

```html
<iframe
  width="178" height="24" style="border:0px"
  src="http://steveklabnik.github.io/rust-community-versions/2013/10/18/pointers-in-rust-a-guide.html">
</iframe>
```

Please help ensure your own blog posts are correctly flagged by add a badge
when you publish.

Linking to a URL that does not exist, such as before your
PR with the new badge is merged, will simply result in a blank space. As
soon as the PR is merged and GitHub pages updates, the badge will appear.
