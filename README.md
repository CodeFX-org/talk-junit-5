# JUnit 5 - Next Generation Testing on the JVM

The slides for a talk walking you through JUnit 5's features, extension model and architecture.

The slides are written with the awesome
 [Asciidoctor](http://asciidoctor.org/) and visualized with
 [reveal.js](http://asciidoctor.org/).
Thanks to GitHub Pages you can see them [here](http://codefx-org.github.io/talk-junit-5/).

## Repository Structure

Some amlagam of
 [submodules](https://git-scm.com/book/en/v2/Git-Tools-Submodules) and
 [worktrees](https://git-scm.com/docs/git-worktree)...

* `master`
	* `asciidoctor-reveal.js` (submodule ~>
		[CodeFX-org/asciidoctor-reveal.js; nipa](https://github.com/CodeFX-org/asciidoctor-reveal.js/tree/nipa))
	* meta-information (LICENSE, README, Guardfile, ...)
	* presentation in source form
* `gh-pages`
	* `reveal.js` (submodule ~>
		[CodeFX-org/reveal.js; nipa](https://github.com/CodeFX-org/reveal.js/tree/nipa))
	* `highlight.js` (downloaded from [highlightjs.org](https://highlightjs.org/download/) and [source](https://github.com/isagalaev/highlight.js/tree/master/src/styles))
	* presentation in HTML

After checkout, the `gh-pages` branch should be added as a worktree to `master`:

	git worktree add presentation gh-pages


## Setup

To edit the slides clone the repository, check out `master`, and add `gh-pages` as described above.

To generate the presentation you'll need to
 [install Asciidoctor](http://asciidoctor.org/docs/install-toolchain/)
 and run this in the repository's root:

	asciidoctor -T asciidoctor-reveal.js/templates/slim presentation.adoc -o presentation/index.html

If you want to automate that, you can install [guard](https://rubygems.org/gems/guard/versions/2.13.0) and run `guard start` in the same folder.

Finally, to edit the schema do
 a [full setup for reveal.js](https://github.com/hakimel/reveal.js#full-setup)
 in `presentation/reveal.js`.
Here, `grunt serve` will automatically pick up changes in
 `presentation/reveal.js/css/theme/source` and create the CSS files in the correct location.
