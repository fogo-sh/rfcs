- Project / Feature Name: csb-datalake
- Start Date: YYYY-MM-DD) 2026-02-15
- RFC PR: [fogo-sh/rfcs#3](https://github.com/fogo-sh/rfcs/pull/3)

# Summary

[summary]: #summary

Throughout the history of CSB, we have created many websites, many bots, many events, many things.

One common theme, has been things around the collection of data.

Our most popular / active projects being [Scribe](https://github.com/nint8835/scribe), the Discord quotes bot.

However, there has been countless other ideas / attempts / etc. over the years to do similar data collections,
such as:
- [almanac](https://github.com/fogo-sh/almanac): A replacement for the CSBWiki, sort of MediaWiki meets Obsidian,
  for more written content than things with structure/schema.
- [grackdb](https://github.com/fogo-sh/grackdb): What projects have we worked on, who has worked on what, what
  technologies are certain projects written in, which ones are alive/dead/replaced by/etc.?
- [bogos](https://github.com/fogo-sh/bogos): Album upload and nice display software.
- [distributed-library](https://github.com/fogo-sh/distributed-library): What books do we all have, such that
  we could maybe borrow each others books and know who has what book.

Almanac is the cloest one to not being 'dead' as it was updated semi-recently, and Jack worked on
[marky](https://github.com/jackharrhy/marky), the intended multiplayer editor for Almanac, but even that
feels like a stretch, the rest of them are basically either dead, or never shipped.

TODO finish summary

# Motivation

[motivation]: #motivation

We like collecting, disseminating, cataloging, viewing, and even ranking our data, we've had 'failed' approaches
to this in the past, but also some wins, so lets see if we can figure something out that brings back ideas behind
old projects, in a way that should be easier to manage.

# Drawbacks

[drawbacks]: #drawbacks

Its work to do this, we could [XKCD 927](https://xkcd.com/927/) us into yet another solution.

TODO discuss more

# Alternatives and Prior art

[alternatives-and-prior-art]: #alternatives-and-prior-art

TODO discuss

# Unresolved questions

[unresolved-questions]: #unresolved-questions

TODO discuss

# High-level technical overview

[high-level-technical-overview]: #high-level-technical-overview

Take (very high level) pointers from how things work in the [ATProto](https://atproto.com/) space, mostly from
data being this thing that exists at a higher level than the applications built around viewing and creating that
data.

TODO write more, explain / flesh out this concept.

# Involvement

[involvement]: #involvement

Jack: wants to define the initial 'schema' for this, and make some choices of the technical design of the 'base'
that the apps / views can spawn from.

TODO: find others who want to collab.
