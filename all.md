---
layout: page
---
<div class="profile">
	{% if site.logourl != "" %}<img src="{{ site.logourl }}" class="profileimage" alt="user">{% endif %}
	<h4>{{ site.title }}</h4>
	<p>{{ site.description }}</p>
	<hr>
</div>


<section class="post-list">
  <h2> Article Index </h2>
  <ul style="list-style-type: none;">
	{% for post in site.posts %}
	<!--			<h2>
					{% for category in post.categories %}
					{{ category }} 
					{% endfor %} 
				</h2>-->
				<li >
				  <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        </li>
	{% endfor %}
  </ul>

</section>
