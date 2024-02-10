---
layout: page
title: About
permalink: /about/
---

<div class="center">
    <a href="{{ site.baseurl }}/" title="link to home of {{ site.title }}">
        <img src="{{ site.baseurl }}/assets/images/profile.jpeg" class="user-image center" alt="My Profile Photo">
    </a>

</div>
<div class="center">
<h1> {{ site.title_tr }}</h1>
<h6 > People often tell me pronounciation of my name is hard. Help arrived! </h6>
<audio controls>
    <source src="{{ site.baseurl }}/assets/name.mp3" type="audio/mpeg">
    Your browser does not support the audio element.
</audio>

<div class="social-links">
    {%- include social.html -%}
</div>

</div>
