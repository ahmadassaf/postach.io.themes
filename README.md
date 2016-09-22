## Postach.io Themes

This repository contains the various [Postach.io](http://postach.io) themes that i use for:

 - [moodboard.ahmadassaf.com](moodboard.ahmadassaf.com): Contains various UIs and interesting designs i come across the web
 - [food.ahmadassaf.com](food.ahmadassaf.com): Contains curated food recipes that i like
 - [readings.ahmadassaf.com](readings.ahmadassaf.com): Contains interesting readings and articles i come across

 All the websites have Google Analytics set up internally by:

```html
    {% if site.analytics %}
    <script type="text/javascript">
        var _gaq = _gaq || [];
          _gaq.push(['_setAccount', '{{ site.analytics }}']);
          _gaq.push(['_trackPageview']);
          (function() {
            var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true;
            ga.src = 'https://ssl.google-analytics.com/ga.js';
            var s = document.getElementsByTagName('script')[0]; s.parentNode.insertBefore(ga, s);
          })();
    </script>
    {% endif %}
```

where `{% site.analytics %}` is defined in each site's settings page. Similarily, Disquss comments can be loaded if enabled via the `{% site.disqus %}` setting and then the following:

```html
<div id="disqus_thread"></div>
<script type="text/javascript">
    var disqus_shortname = '{{ site.disqus }}';
    var disqus_url = '{{site.base_url}}{{ post.url }}';
    (function() {
      var dsq = document.createElement('script'); dsq.type = 'text/javascript'; dsq.async = true;
      dsq.src = 'http://' + disqus_shortname + '.disqus.com/embed.js';
      (document.getElementsByTagName('head')[0] || document.getElementsByTagName('body')[0]).appendChild(dsq);
    })();
</script>
```

