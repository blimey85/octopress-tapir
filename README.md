# octopress-tapir #

[Tapir](http://tapirgo.com/) search for your [Octopress](http://octopress.org/) blog!

Tapir works by indexing your RSS feed. Only what is included within this file will be indexed. For RSS purposes you most
likely only want the last 20 or so articles but for search, you want all of them included. To handle this, we simply
create a second xml file to use for search.

`atom.xml`

* the original file
* limited to 20 most recent posts
* we use this for RSS

`atom_search.xml`

* the new file
* a modified version of atom.xml
* includes all posts
* added summary field

##Install
1. Visit [Tapirgo.com](http://tapirgo.com) and enter the url to your atom_search.xml like:
`http://yoursite.com/atom_search.xml`<br>After you enter your email and click the big GO button, you'll be given both a public and a private token.
2. Open your `_config.yml` and include the public token: `tapir_token: your_id_here`
3. Copy `loading.gif` to your `source/images/` folder.
4. Copy `jquery-tapir.js` to your `source/javascripts/` folder.
5. Copy `search.html` to your `source/` folder.
6. Open `source/_includes/navigation.html` and add:

```
{% if site.tapir_token %}
  <form method="get" action="{{ root_url }}/search.html">
    <fieldset role="search">
      <input class="search" name="query" type="text" placeholder="Search..." x-webkit-speech />
    </fieldset>
  </form>
{% endif %}
```
That's all there is to it. You should now be able to search your content using the wonderful [Tapir](http://tapirgo.com/) service. :)

##Author

Gary Traffanstedt (blimey85@gmail.com)<br>
based on the wonderful work of Pankaj Kumar (me@panks.me) and his [Fabric Theme](https://github.com/panks/fabric) for [Octopress](http://octopress.org/).
