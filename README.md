# Keep a CHANGELOG

## Don’t let your friends dump git logs into CHANGELOGs™

### What’s a change log?
A change log is a file which contains a curated, chronologically ordered
list of notable changes for each version of an open source project.

<a href="CHANGELOG.md" title="An example of a CHANGELOG file."><iframe src="CHANGELOG.md" width="570" height="350" seamless="seamless" style="border: 1px solid #aaa; padding: 1em; margin: 0 0.5em;"></iframe></a>

### What’s the point of a change log?
To make it easier for users and contributors to see precisely what
notable changes have been made between each release (or version) of the project.

### Why should I care?
Because software tools are for people. If you don’t care, why are
you contributing to open source? Surely, there must be a kernel (ha!)
of care somewhere in that lovely little brain of yours.

I [talked with Adam Stacoviak and Jerod Santo on The Changelog][thechangelog]
(fitting, right?) podcast about why open source maintainers and
contributors should care, and the motivations behind this project.
If you can spare the time (1:06), it’s a good listen.

### What makes a good change log?
I’m glad you asked.

A good change log sticks to these principles:

- It’s made for humans, not machines, so legibility is crucial.
- Easy to link to any section (hence Markdown over plain text).
- One sub-section per version.
- List releases in reverse-chronological order (newest on top).
- Write all dates in `YYYY-MM-DD` format. (Example: `2012-06-02` for `June 2nd, 2012`.) It’s international, [sensible](http://xkcd.com/1179/), and language-independent.
- Explicitly mention whether the project follows [Semantic Versioning][semver].
- Each version should:
  - List its release date in the above format.
  - Group changes to describe their impact on the project, as follows:
    - `Added` for new features.
    - `Changed` for changes in existing functionality.
    - `Deprecated` for once-stable features removed in upcoming releases.
    - `Removed` for deprecated features removed in this release.
    - `Fixed` for any bug fixes.
    - `Security` to invite users to upgrade in case of vulnerabilities.

### How can I minimize the effort required?
Always have an `"Unreleased"` section at the top for keeping track of any
changes.

This serves two purposes:

- People can see what changes they might expect in upcoming releases
- At release time, you just have to change `"Unreleased"` to the version number
  and add a new `"Unreleased"` header at the top.

### What makes unicorns cry?
Alright…let’s get into it.

- **Dumping a diff of commit logs.** Just don’t do that, you’re helping nobody.
- **Not emphasizing deprecations.** When people upgrade from one version to
  another, it should be painfully clear when something will break.
- **Dates in region-specific formats.** Americans put the month first
  ("06-02-2012" for June 2nd, 2012, which makes *no* sense), while Brits
  use a robotic-looking "2 June 2012", yet pronounce it differently.
  "2012-06-02" works logically from largest to smallest, doesn't overlap in
  ambiguous ways with other date formats, and is an
  [ISO standard](http://www.iso.org/iso/home/standards/iso8601.htm). Thus, it
  is the recommended date format for change logs.

There’s more. Help me collect those unicorn tears by
[opening an issue][issues]
or a pull request.

### Is there a standard change log format?
Sadly, no. Calm down. I know you're furiously rushing to find that link
to the GNU change log style guide, or the two-paragraph GNU NEWS file
"guideline". The GNU style guide is a nice start but it is naive.
There's nothing wrong with being naive but when people need
guidance it's rarely very helpful. Especially when there are many
situations and edge cases to deal with.

This project [contains what I hope will become a better CHANGELOG file convention][CHANGELOG]
for all open source projects. Can the open source community learn from
its mistake and not act as if the ten commandments were written long ago
and got everything right? Alright. So please take a look around and
remember that [discussions and suggestions for improvements are welcome][issues]!

### What should the change log file be named?
Well, if you can’t tell from the example above, `CHANGELOG.md` is the
best convention so far.

Some projects also use `HISTORY.txt`, `HISTORY.md`, `History.md`, `NEWS.txt`,
`NEWS.md`, `News.txt`, `RELEASES.txt`, `RELEASE.md`, `releases.md`, etc.

It’s a mess. All these names only makes it harder for people to find it.

### Why can’t people just use a `git log` diff?
Because log diffs are full of noise. Can we really expect every single
commit in an open source project to be meaningful and self-explanatory?
That seems like a pipe dream.

### Can change logs be automatically parsed?
It’s difficult, because people follow wildly different formats and file names.

[Vandamme][vandamme] is a Ruby gem
created by the [Gemnasium][gemnasium] team and which parses
many (but not all) open source project change logs.

### Why do you alternate between spelling it "CHANGELOG" and "change log"?
"CHANGELOG" is the name of the file itself. It's a bit shouty but it's a
historical convention followed by many open source project. Other
examples of similar files include [`README`](README.md), [`LICENSE`](LICENSE),
and [`CONTRIBUTING`](CONTRIBUTING.md).

The uppercase naming (which in old operating systems made these files stick
to the top) is used to draw attention to them. Since they're important
metadata about the project, they could be useful to anyone intending to use
or contribute to it, much like [open source project badges][shields].

When I refer to a "change log", I'm talking about the function of this
file: to log changes.

### What about yanked releases?
Yanked releases are versions that had to be pulled because of a serious
bug or security issue. Often these versions don't even appear in change
logs. They should. This is how you should display them:

`## 0.0.5 - 2014-12-13 [YANKED]`

The `[YANKED]` tag is loud for a reason. It's important for people to
notice it. Since it's surrounded by brackets it's also easier to parse
programmatically.

### How can I contribute?
This document is not the **truth**; it’s my carefully considered
opinion, along with information and examples I gathered.
Although I provide an actual [CHANGELOG][] on [the GitHub repo][gh],
I have purposefully not created a proper *release* or clear list of rules
to follow (as [SemVer.org][semver] does, for instance).

This is because I want our community to reach a consensus. I believe the
discussion is as important as the end result.

So please [**pitch in**][gh].

[CHANGELOG]: ./CHANGELOG.md
[gemnasium]: http://gemnasium.com
[gh]: https://github.com/olivierlacan/keep-a-changelog
[issues]: https://github.com/olivierlacan/keep-a-changelog/issues
[semver]: http://semver.org
[shields]: http://shields.io
[thechangelog]: http://5by5.tv/changelog/127
[vandamme]: https://github.com/tech-angels/vandamme/
