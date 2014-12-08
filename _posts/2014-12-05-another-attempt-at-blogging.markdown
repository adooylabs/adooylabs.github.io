---
layout: post
title: "Another Attempt at Blogging"
date: 2014-12-05 13:20:00
categories: misc
---
I have too much failed attempts at blogging from `wordpress` to `tumblr`, and countless others. They were great softwares and have great features but none of them fit the mold. I need something simple, something in that has less updates and less vulnerabilities. And yet something efficient and most of all free from those hosting fees.

Along came Jekyll, a ruby gem that generates static websitse. Transforming markdown files into posts and pages. No more database, no more updates, and it is blog-aware. And best of all free hosting, if you deploy it on `github-pages`.

I think 'Jekyll' is perfect for developers. You can use your favorite`text-editor` to write post and pages, and `git` to deploy your latest changes. It also comes with a good syntax highlighter with
`Pygments` or `Rouge`.

{% highlight ruby linenos %}
def print_msg(message)
  puts "Hello, World!  #{message}"
end

print_msg('How are you?')
#=> prints 'Hello, World! How are you?' to STDOUT
{% endhighlight %}

So, yeah. I'm  excited about my new setup. If you have tips and tricks on `Jekyll`. Leave a comment below.
