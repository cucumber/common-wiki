[The documentation has moved](https://docs.cucumber.io/).

Please do not make further edits to this Wiki.

**Note:** If this page contains information that is useful to you, please consider adding it to the docs project on GitHub.

===================================================================


h2. Install

Cucumber can be used with "Merb":http://merbivore.com/ via the "merb_cucumber":http://github.com/roman/merb_cucumber plugin.

To install merb_cucumber:

<pre>sudo gem install david-merb_cucumber</pre>

Or you can install "jsmestad-merb_cucumber":http://github.com/jsmestad/merb_cucumber

<pre>sudo gem install jsmestad-merb_cucumber</pre>

Here is a brief note from jsmestad.

bq. Note – you must uninstall david-merb_cucumber in order for this gem to take precedence. Merb + Cucumber + Webrat testing stack. Builds upon David’s work, but binds Webrat as a dependency to hopefully ensure a smooth upgrade for future Webrat releases. Also Factory_Girl generators will be added soon.

Here's a better one

<pre>sudo gem install roman-merb_cucumber</pre>

bq. Note – both justin's and david's merb_cucumber forks didnt work for me (they don't seem to use the bundled directory). Try Roman's


h2. Usage

The inside of a merb application directory, try:

<pre>
merb-gen cucumber
merb-gen feature FEATURE_NAME
</pre>

Edit your feature, and:

<pre>rake features</pre>

h2. Tips

Describe can use multiple given blocks

For example, you can "now":http://ln-s.net/2vB2
(since Feb 26, 2009 commit by carllerche) write

<pre><code>
given "some food" do
  @food = "pizza"
end

given "some drink" do
  @drink = "beer"
end

describe "Something", :given => ["some food", "some drink"] do
  it "should have dinner" do
    # has @food and @drink set to pizza and beer, respectively
  end
end
</code></pre>

h2. Looking for Examples?

So am I. Therefore I've been scrounging github in search of some. There are many merb projects out there with empty /features sitting around so searching github can potentially return many false positives. 

But, please add some when you find them! 

Here are some merb projects that use cucumber (feel free to add/update/delete this list accordingly, I did not rigorously weed through each one but I did only include /features that had actual substantial or interesting/creative examples):

* "http://github.com/matthewford/comic-review/tree/master":http://github.com/matthewford/comic-review/tree/master
* "http://github.com/teamon/merb-base/tree/master":http://github.com/teamon/merb-base/tree/master
* "http://github.com/mop/mini-blog/tree/master":http://github.com/mop/mini-blog/tree/master
* "http://github.com/jnicklas/merb_upload/tree/master":http://github.com/jnicklas/merb_upload/tree/master
* "http://github.com/ngty/ty_cucumber_salad/tree/master":http://github.com/ngty/ty_cucumber_salad/tree/master
* "http://github.com/teamon/aliquam/tree/master":http://github.com/teamon/aliquam/tree/master
* cucumber in a merb slice: "http://github.com/balinterdi/philotes/tree/master":http://github.com/balinterdi/philotes/tree/master
* "http://github.com/wolfmanjm/wolfmanblog/tree/master":http://github.com/wolfmanjm/wolfmanblog/tree/master

h2. Tutorials

* Full-Cycle Feature Development in Merb: "Ruby Advent 2008 Article written by Foy Savas":http://advent2008.hackruby.com/past/2008/12/18/fullcycle_feature_development_in_merb.html
* Merb-Book cucumber chapter: "http://book.merbist.com/testing-your-application/cucumber":http://book.merbist.com/testing-your-application/cucumber
* "Writing User Stories with merb_cucumber":http://dermological.blogspot.com/2008/11/writing-user-stories-with-merb-cucumber.html