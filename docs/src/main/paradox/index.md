Paradox
=======

Paradox is a Markdown documentation tool for software projects.
The Github repo is [lightbend/paradox][repo].

**Paradox is NOT supported under Lightbend subscription.**

### Setup

Find [the latest](https://github.com/lightbend/paradox/releases) version, and create `project/paradox.sbt`:

```scala
addSbtPlugin("com.lightbend.paradox" % "sbt-paradox" % "X.Y.Z")
```

Inside `build.sbt`, add `ParadoxPlugin` to a subproject:

```scala
lazy val root = (project in file(".")).
  enablePlugins(ParadoxPlugin).
  settings(
    name := "Hello Project",
    paradoxTheme := Some(builtinParadoxTheme("generic"))
  )
```

Then call `paradox` which will generate the site in `target/paradox/site/`.

Your markdown documentation will go inside `src/main/paradox/`. For example, you can start with `src/main/paradox/index.md`.

### Key features

- Supports Github flavored Markdown powered by [Pegdown][].
- Principled markdown exntension using generic directives syntax.
- Github-friendly Markdown source (links work).
- Code snippet inclusion for compilable code examples.
- Templating and theming.

### Generic directive

Paradox extends Markdown in a principled manner called generic directives syntax,
which basically means that all of our extensions would start with `@` (for inline), `@@` (leaf block), or `@@@` (container block).

### License and credits

- Copyright 2015-2016 Lightbend, Inc. Paradox is provided under the Apache 2.0 license.
- The markdown engine is based on Mathias's [Pegdown][].

@@@ index

* [Organizing pages](features/organizing-pages.md)
* [Linking](features/linking.md)
* [Snippet inclusion](features/snippet-inclusion.md)
* [Templating](features/templating.md)

@@@

  [Pegdown]: https://github.com/sirthias/pegdown/
  [repo]: https://github.com/lightbend/paradox