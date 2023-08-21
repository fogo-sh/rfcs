- Project / Feature Name: `compsci-bois-almanac`
- Start Date: 2023-08-17
- RFC PR: [fogo-sh/rfcs#1](https://github.com/fogo-sh/rfcs/pull/1)

# Summary

[summary]: #summary

A collection of markdown files about different events / things / memes / etc. in the Compsci-Boi-verse, accessible over
http(s) and gemini, privately.

Images and videos will be supported, but it will be mostly text.

The initial content can be populated from a XML export of the existing Compsci Bois Wiki.

Backlinks will be supported via \[\[this syntax\]\].

After the initial version is released, more syntax can be added to increase more wiki-like functionality, like
categories / dates / other enriching metadata, along then with pages that can act as indexes that utilize the metadata
(like a all categories page, or an all posts about events in 2023).

# Motivation

[motivation]: #motivation

Having a location to document different things about our group, from a nostalgic / historical perspective, would be
nice.

Hopefully, due to the enjoyment of consuming even the existing content of this resource that comes from the existing
wiki in this new more accessible to programmer format will encourage more people to contribute to it.

["The Space Between Us"](https://goodenough.us/blog/2023-08-18-the-space-between-us/) is a good blog post about the
creation of content to form 'identity anchors'.

["File over app"](https://stephanango.com/file-over-app) gives rationale why having the underlying data the
application stores as files.

> _File over app is an appeal to tool makers: accept that all software is ephemeral, and give people ownership over
> their data._

# Drawbacks

[drawbacks]: #drawbacks

We already technically have a wiki solution, [fogo-sh/CSBWiki](https://github.com/fogo-sh/CSBWiki), and MediaWiki is
quite powerful.

This proposal implies building a bespoke solution, harder than just finding something and running with it.

# Alternatives and Prior art

[alternatives-and-prior-art]: #alternatives-and-prior-art

What already exists to solve this problem, potentially in a different form, and why is it not sufficient?

- https://git.sr.ht/~m15o/ni - Ni is a static wiki generator. It allows you to write files that reference each other,
  and to generate an html output that includes links and back links.

- https://git.sr.ht/~m15o/nini - nini is a static wiki generator. It generates pages that include backlinks to other
  ages.

- https://obsidian.md/publish - Obsidian Publish

- https://obsidian.md/ / https://logseq.com/ / https://roamresearch.com/

# Unresolved questions

[unresolved-questions]: #unresolved-questions

- Where will this be hosted?
- Does it make to host this in one location, or maybe many, for the sake of redundancy?
- What sort of authentication will be used to keep the publicly hosted versions of the site private?

# High-level technical overview

[high-level-technical-overview]: #high-level-technical-overview

- Write in Go

  - Low level-ish
  - Decent standard library
  - KISS - keep it simple, stupid

- A cli, that can be used to:

  - produce a static .html output of the almanac
  - host a dev server that autorebuilds / autoreloads when files are changed on disk
  - host a gemini server

- The data on disk can be read into in-memory data structures, and all of the generation of the output can happen with
  it in this state, and then written to disk, basically a deserialization and serialization step.

```
                   ┌─────┐       ┌───────────────┐
                   │ ... │◄─┐  ┌►│ Gemini Server │
                   └─────┘  │  │ └───────────────┘
                            │  │
  ┌──────────┐     ┌────────┴──┴─────────────────┐
  │ Markdown │ ──► │ Intermediate Representation │
  └──────────┘     └────────────┬────┬───────────┘
                                │    │
                   ┌────────────▼┐  ┌▼───────────┐
                   │ Static HTML │  │ Dev Server │
                   └─────────────┘  └────────────┘
```

# Involvement

[involvement]: #involvement

Developers:

- Jack

Contributors:

- TODO

Stakeholders:

- The CompSci Bois
