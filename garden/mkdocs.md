# MkDocs

These pages are rendered using [`MkDocs`](https://www.mkdocs.org/), a tool
originally intended to publish documentation for technical projects.

However, it can be used to generate static sites in general.

I was inspired to follow this strategy after seeing
[Tiger's Digital Garden](https://ynotstartups.github.io/), which uses the same
tool.

## Why did I like this idea ?

`MkDocs` works by rendering `Markdown` files to generate each of the site's
pages. I'm very used to writing documentation using `Markdown` after years
working on tech projects.

I like working with `Markdown` because it's very simple and allows me to focus
on the content rather than the format of the text.

Usually blog-like pages rely on complex user-interfaces to tweak almost every
detail of the site. I only need Vim (my preferred text editor) to add new notes
to this site.

`MkDocs` also comes with built-in support to upload the generated site directly
to GitHub Pages, which I'm using for hosting. That's one technical complexity
less to distract me from the actual content.

Since `MkDocs` original intent is sharing technical documentation, the site
gets some navigational features for free, like the list of notes, the table of
contents, the text search, etc. Which I think are very useful for exploring
this kind of mental notes, while being simple enough to not get in the way.

Since the source files are basically text files, I can use `git` to keep
a history of the changes, in case I need to come back and review some previous
version or revert any changes.

The same source files can be made available in a public repository in
[GitHub](https://github.com/JoseKilo/garden/), which allows the history and
tools configuration to be shared. I think this aligns with the goal of [working
with the garage door
up](https://notes.andymatuschak.org/z21cgR9K3UcQ5a7yPsj2RUim3oM2TzdBByZu).
