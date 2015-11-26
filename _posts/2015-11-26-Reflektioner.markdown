* What do you think of pre-compiling your CSS?
    * Compare to regular CSS
    * Which techniques did you use?
    * Pros and cons?

Jag har upplevt SCSS som ett fantastiskt smidigt komplement till traditionell CSS. Jag har framförallt använt mig av variabeldeklarationer för att kunna återanvända sajt-omfattande egenskaper (typ fonts och färger) och nästlade uttryck, i stil med:

{% highlight SCSS %} a { color: $baseColor;

&:hover {
    color: $highlight;
}
} {% endhighlight %}

Jag tycker också att det känts väldigt självklart att använda partials och imports för att minska ner på antalet http-anrop. För min väldigt simpla design har jag inte använt mig av mixins.

What do you think of static site generators?

What type of projects are they suitable for?
Än så länge upplever jag att SSG:er är en otroligt smidig approach till att få upp statiskt innehåll snabbt. Jag hade dock inga problem att få upp en fungerande utvecklingsstack, men hade jag haft det, skulle jag nog ha en annan syn på saken.

What is robots.txt and how have you configure it for your site?
robots.txt är en fil som ger information till besökande indexeringsrobotar om vilka (om några) delar av ens site man vill hålla utanför deras indexering. Roboten väljer själv om den ska följa instruktionerna. Jag har valt att dela med mig av det mesta, genom inställningen

{% highlight HTML %}

User-agent: * Disallow: /assets/

{% endhighlight %}

som tillåter indexering av allt utom katalogen assets, där jag förvarar alla sitens bilder.

What is humans.txt and how have you configure it for your site?
humans.txt är till för att ge något slags utrymme för personerna bakom en site att presentera sig. Min ser ut så här:

{% highlight HTML %} /* TEAM */ By: Fredrik Wällstedt Site: http://klaathulhu.github.io Location: Lund, Sweden

/* SITE */ Site Name: Klaathulhu's site Site URL: http://klaathulhu.github.io Langauge: swedish/english {% endhighlight %}

How did you implements comments to blog posts
För kommentarsfunktionen har jag använt disqus, som jag har kopplat till blogposterna. För att få det att fungera skapade jag ett konto hos disqus och kopierade in den aktuella kod-snippeten i layoutdokumentet för poster, samt bytte ut lämpliga värden mot de, för min site, aktuella motsvarigheterna.

What is Open Graph and how do you make use of it?
Open Graph är ett protokoll för social delning, som underlättar delning på exempelvis Facebook. Jag har använt det med följande HTML:

{% highlight HTML %}

<meta property="og:title" content="The code of Klaathulhu" />
<meta property="og:url" content="http://klaathulhu.github.io" />
<meta property="og:type" content="website" />
<meta property="og:description" content="Quiet possibly a working draft by Fredrik Wällstedt" />
<meta property="og:image" content="http://klaathulhu.github.io/assets/img/squid.png" />

<!-- Twitter data -->
<meta name="twitter:card" content="summary" />
<meta name="twitter:title" content="The code of Klaathulhu" />
<meta name="twitter:description" content="Quiet possibly a working draft by Fredrik Wällstedt" />
<meta name="twitter:url" content="http://klaathulhu.github.io" />
<meta name="twitter:image" content="http://klaathulhu.github.io/assets/img/squid.png" />
{% endhighlight %}
