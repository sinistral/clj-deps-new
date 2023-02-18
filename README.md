# clj-deps-new

A [`deps-new`][deps-new] template for a clean, minimalist [`deps`][deps]-based
Clojure library project.

## Motivation

Initializers like [`lein new`][lein] and [`deps-new`][deps-new] are an
invaluable community resource that make it possible for - especially new -
Clojurians to bootstrap a project that encourages best practices; I benefited
greatly while getting started.  Over time - as one becomes more comfortable with
the best practices of maintaining projects in the ecosystem - I believe there is
value in having a minimal initial configuration that can immediately be
published with seeming unkempt; that is: initially sparse is better than
apparently unfinished.

Thus, `clj-deps-new` generates only what is minimally necessary, forgoing
`FIXME`s and `TODO`s and allowing features to be added to a project
incrementally as they are needed, rather than having to removed at the start
while they are not.

Similarly, I find the long-standing attachment to naming (that exists purely for
historical reasons, as far as I can tell) with arbitrary contractions and
pluralisation an unnecessary anchor.  Certainly, consistency and patterns are
important to reduce friction, but the tooling available makes the impact of
improving the situation with a more pleasing layout virtually zero.

The changes applied here create the following top-level project directory
layout:

 - resource
 - source
 - test

The contraction of `src` is unnecessarily inconsistent with both `test` and
`resources`.  The pluralization of `resources` is itself again arbitrarily
inconsistent with `source`, and `doc`.

## Usage

`clj-deps-new` is a custom template for, and requires, Sean Corfield's
`deps-new` that should be installed as the Clojure CLI tool `new`.  To generate
a new project, use an incantation of the form (on macOS):

```sh
clojure -Sdeps \
  '{:deps {io.github.sinistral/clj-deps-new {:git/sha "..."}}}' \
  -Tnew create \
  :template $(id -un)/clj-deps-new \
  :name $(id -un)/foo \
  :developer "\"$(id -F)\""
```

Please see the [`deps-new`][deps-new] documentation for all [available
options](https://github.com/seancorfield/deps-new/blob/develop/doc/options.md).

## Next steps

As your project grows and matures, consider incorporating the following best
practises:

 * Choose an appropriate licence.  Private/internal projects may choose to forgo
   a licence altogether, while others may elect to use an open licence like the
   EPL 1.0 that is the standard for Clojure projects.
   * Install a plain-text LICENSE file in the root of your repository that
     contains the text for your chosen licence, and
   * Update your README accordingly.
 * Write [great documentation](http://jacobian.org/writing/what-to-write/).
 * Add a [change log](http://keepachangelog.com/) to help humans understand how
   new versions may impact (or have impacted) their usage of your library.

## Licence

Copyright © 2023 Marc Daya

Distributed under the [BSD 2-Clause Licence][bsd2].

[bsd2]: https://opensource.org/license/bsd-2-clause/
[deps]: https://clojure.org/guides/deps_and_cli
[deps-new]: https://github.com/seancorfield/deps-new
[epl1]: https://opensource.org/license/eclipse-1-0-php/
[lein]: https://leiningen.org/#
