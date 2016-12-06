# RIGHT, JEKYLL THEN

<head>
    * stylesheet
    * Merriweather
    * Spinnaker
    * Fanwood
    * jekyll-seo-tags
</head>
<body>
    <header>
        * Title
        * Tagline
        * <nav></nav>
    </header>
    <main>
        <article>
        * Post ()
            - Date
            - Title
            - Subtitle
            - Prefatory material {{ post.prefatory | markdownify }}
            - Drop cap
            - Content
            - Author name links to "Wait Who"
        </article>
        * Comments via Staticman
            - I kinda like the HTML5 stuff they've got going on at NC
            - ol > li > article > ( header > cite ) + article
        <aside>
            * Sidebar
                - Stylin' Archive (see below)
                - Search box - DDG?
        </aside>
        <nav>
            * "Now Where?" box
                - Prev. post, w/ date
                - Next post, w/ date
                - "Show archive" for small screens... hm, that seems to be in the wrong place. Separate page?
        </nav>
    </main>
    <footer>
    * Something about me and something about Jekyll and GitHub
    * RSS feed link
    </footer>
</body>

Elsewhere: jekyll-feed



The stylin' archive
```
{{ for num in (1..100) }}
    {{ for post in site.posts | where_exp: "post.year == 2100 - num" }}
        {{ post.year }}, {{ post.month }}, {{ post.title }}, 
        and some other stuff
    {{ endfor }}
{{ endfor }}
```

Things to use
* figure.html from Alembic
* Staticman code from MMistakes

Things to do
* Query WP database for comments
* Replace all those silly "#### nbsp;" things with -----
* Probably be good to replace those HTML escape code things too
      sed -e 's/&#8216;/‘/g'
      sed -e 's/&#8217;/’/g'
      sed -e 's/&#8220;/“/g'
      sed -e 's/&#8221;/”/g'
      sed -e 's/&#8211;/--/g'
      sed -e 's/&#8212;/---/g'
      sed -e 's/#### nbsp;/-----/g'
* Change old image tags? 'Cause Blogger's markup is seriously ugly as sin