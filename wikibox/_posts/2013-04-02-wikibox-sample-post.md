---
layout: post
category: cat001
comments: false
date: 2013-04-02 21:35 (created)
edit: 2012-05-04  (changed)
title: Syntax Sample Post
tags: ' #box(name) #board(name) #toc #star #prio(1) #study(5) #cat(dev) #public #share(Person)'
line: Line can be used as description, synopsis, abstract, subtitle, preview, teaser or question answered in content. So this line can be very useful in many ways.
box: wikibox
---
# Heading 1

Suspendisse sagittis dui in nisi feugiat ut semper ante viverra. Vestibulum quam dui, hendrerit sed lacinia a, lacinia id sapien. Nulla id nunc ut quam facilisis scelerisque. Aenean et velit ante. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque pharetra erat at augue elementum id tempor ipsum lacinia. Vivamus id tortor mi, ac porttitor arcu. Sed nec eros sem, et suscipit erat. Vivamus viverra felis at elit laoreet mattis. Cras dapibus facilisis mauris ut ultricies. Donec lectus metus, consequat pulvinar congue sed, tempus eu elit. Proin id lacinia magna. Sed imperdiet dui eu turpis tristique ultricies. Cras ullamcorper tempor nisl, ac porta purus hendrerit at. Phasellus in hendrerit dui.

## Heading 2
### Heading 3    
#### Heading 4

# Unordered List

- Maecenas non odio vitae tortor blandit posuere
- Duis ac leo quis mi blandit molestie.
- Vestibulum sodales dignissim neque, eget pharetra metus adipiscing id. 
- Morbi et metus quam, et sagittis risus. 

# Ordered List

1. Maecenas non odio vitae tortor blandit posuere
- Duis ac leo quis mi blandit molestie.
- Vestibulum sodales dignissim neque, eget pharetra metus adipiscing id. 
- Morbi et metus quam, et sagittis risus.

# Internal Links

- <a href="/box004/2013-01-02-box4-post4">HTML Link to Post 4 in Box 4</a>
- [Liquids Markdown Link to Post 4 in Box 4]({{ site.url }}/box004/2013-01-02-box4-post4)
- [Markdown Link to Post 4 in Box 4](/box004/2013-01-02-box4-post4)
- [Offline relative Markdown Link to Post 4 in Box 4](../../box004/2013-01-02-box4-post4/index.html)

# Pygments

{% highlight html %}
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
{% endhighlight %}

{% highlight python %}
s = "Python syntax highlighting"
print s
{% endhighlight %}
 
{% highlight ruby linenos %}
var s = "JavaScript syntax highlighting";
alert(s);
{% endhighlight %}

# Highligtht.JS

<pre><code class="html">No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
</code></pre>

<pre><code class="pyhton">s = "Python syntax highlighting"
print s
</code></pre>
 
<pre>
<code class>var s = "JavaScript syntax highlighting";
alert(s);
</code></pre>

# Fenced Code Blocks

```
No language indicated, so no syntax highlighting. 
But let's throw in a <b>tag</b>.
```

```python
s = "Python syntax highlighting"
print s
````
 
```
var s = "JavaScript syntax highlighting";
alert(s);
```

