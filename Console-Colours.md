[The documentation has moved](https://docs.cucumber.io/).

Please do not make further edits to this Wiki.

**Note:** If this page contains information that is useful to you, please consider adding it to the docs project on GitHub.

===================================================================

The console output for Cucumber colours steps according to how execution went. In addition to that, matched step variables are highlighted. Here is an example of how a single step gets printed:

<notextile>
<pre><span style="color:green">Given I have</span> <span style="color:green;font-weight:bold">487</span> <span style="color:green">cucumbers in my belly</span> <span style="color:grey"># features/vegetable_features.feature:49</span>
</pre></notextile>

You can tweak the colours by defining a <code>$CUCUMBER_COLORS</code> variable in your shell, very much like you can tweak the colours of the familiar POSIX command <code>ls</code> with
"$LSCOLORS or $LS_COLORS":https://geoff.greer.fm/2008/06/27/lscolorsls_colors-now-with-linux-support/.

_Don't attempt to set it in your <code>support/env.rb</code> file or any other Ruby file. It must be defined *before* Cucumber starts. You can do it in your Rakefile with_ <code>ENV['CUCUMBER_COLORS'] = '...'</code>

The colours that you can change are:

|_.Key|_.Default colours|
|undefined|%{color:yellow}yellow% (v0.2.0 and up)|
|pending|%{color:yellow}yellow%|
|pending_param|%{color:yellow;font-weight: bold}yellow,bold%|
|failed|%{color:red}red%|
|failed_param|%{color:red;font-weight: bold}red,bold%|
|passed|%{color:green}green%|
|passed_param|%{color:green;font-weight: bold}green,bold%|
|skipped|%{color:cyan}cyan%|
|skipped_param|%{color:cyan;font-weight: bold}cyan,bold%|
|comment|%{color:grey}grey%|
|tag|%{color:cyan}cyan% (v0.2.0 and up)|

For instance, if your shell has a black background and a green font (like the
"Homebrew" settings for OS X' Terminal.app), you may want to override passed
steps to be white instead of green. Examples:

<pre>export CUCUMBER_COLORS=passed=white
export CUCUMBER_COLORS=passed=white,bold:passed_param=white,bold,underline
</pre>

Aslak likes to highlight all parameters in magenta, so he uses this:

<pre>export CUCUMBER_COLORS=pending_param=magenta:failed_param=magenta:passed_param=magenta:skipped_param=magenta</pre>

(If you're on Windows, use <code>SET</code> instead of <code>export</code>).

To see what colours and effects are available, just run this in your shell:

<pre>ruby -e "require 'rubygems'; require 'term/ansicolor'; puts Term::ANSIColor.attributes"
</pre>

Although not listed in the output, you can also use <code>grey</code>.

h2. Windows

Windows users can get colours by installing "ANSICON":https://github.com/adoxa/ansicon/downloads or "cmder":http://cmder.net/