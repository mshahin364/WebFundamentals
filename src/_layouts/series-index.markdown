<!-- Lets plan out the order of videos -->
{% assign shows = page.articles[page.id] | sort: 'date' | reverse  %}


    {% include head.liquid %}
  </head>

  <body {% if page.rtl == true %}dir="rtl" {% endif %}class="page--{{ page.class }}" itemscope itemtype="http://schema.org/WebSite">

  	<!-- Select Appropriate betterbook -->
    {% injectdata content _betterbook-shows.yaml %}

    {% include header.liquid %}

    {% wrap content %}

	    <h1>{{ page.title }}</h1>

	    <!-- Display content from the markdown -->
	    {{ content }}

	    <h2>Episodes</h2>

	    <ol>
	      {% for show in shows %}
	      	<a href="{{site.baseurl}}{{show.url | canonicalize}}">
	      		<div class="lastestEpisode">
		      		<div class="lastestEpisode--image">
		      			<img src="http://img.youtube.com/vi/{{ show.youtubeVideoID }}/0.jpg" />
		      		</div>
		      		<div class="lastestEpisode--title">
		      			{{ show.title }}
		      		</div>
		      	</div>
	      	</a>
		    {% endfor %}
	    </ol>

    {% endwrap %}

    {% include footer.liquid %}
