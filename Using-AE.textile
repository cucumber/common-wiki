[The documentation has moved](https://docs.cucumber.io/).

Please do not make further edits to this Wiki.

**Note:** If this page contains information that is useful to you, please consider adding it to the docs project on GitHub.

===================================================================

Simple load the @ae@ library.

<pre>
  require 'ae'
</pre>

If you want the subjective forms, then require it as well.

<pre>
  require 'ae'
  require 'ae/should'
</pre>

You do not need to add anything to Cucumber's "World", because AE works at the top-level, rather then simply defining a set of assertion methods.
