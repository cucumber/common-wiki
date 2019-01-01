[The documentation has moved](https://docs.cucumber.io/).

Please do not make further edits to this Wiki.

**Note:** If this page contains information that is useful to you, please consider adding it to the docs project on GitHub.

===================================================================

This is related to problem described in this "ticket":https://webrat.lighthouseapp.com/projects/10503/tickets/168-redirects-in-rails-23-not-being-followed-by-webrat. We faced this problem in webrat <b>0.7</b> while using with subdomain_fu.
<b>Solution.</b>
Defining tld_sizes for subdomain_fu solved this problem.
Create a file called subdomain_fu.rb under config/initializers with following content.
SubdomainFu.tld_sizes = {
    :development => 0, :test => 1, :production => 1, :cucumber => 1
}


Another error <b>You have a nil object when you didn't expect it! </b> when using subdomain with mail url.
"Solution":http://groups.google.com/group/cukes/browse_thread/thread/91efe1ef945ddda3/ba59cd0e7e9aa51f?lnk=gst&q=vijendra#ba59cd0e7e9aa51f
