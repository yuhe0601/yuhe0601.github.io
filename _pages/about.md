---
layout: about
title: About
permalink: /

profile:
  align: right
  image: yuhe.png
  image_circular: false # crops the image to make it circular
  # more_info: >
    # <p style="font-family: 'Source Code Pro', serif; font-size: 18px;">College of Computer Science</p>
    # <p style="font-family: 'Source Code Pro', serif; font-size: 18px;">Northwest University</p>
    # <p style="font-family: 'Source Code Pro', serif; font-size: 18px;">Xi'an, Shaanxi Province</p>


selected_papers: true # includes a list of papers marked as "selected={true}"
social: false # includes social icons at the bottom of the page

announcements:
  enabled: true # includes a list of news items
  scrollable: true # adds a vertical scroll bar if there are more than 3 news items
  limit: 5 # leave blank to include all the news in the `_news` folder

latest_posts:
  enabled: false
  scrollable: true # adds a vertical scroll bar if there are more than 3 new posts items
  limit: 3 # leave blank to include all the blog posts
---

I am **Yuhe Zhang**, an Associate Professor and a PhD supervisor at Northwest University(NWU). I obtained a Bachelor’s degree in Software Engineering and a PhD in Computer Science from NWU. I visited Professor Daniel Cohen-Or’s lab in Israel in 2022. 

My research centres on 3D vision, with particular emphasis on point cloud processing, 3D shape generation, and the digital restoration of cultural heritage. More recently, I have developed a keen interest in 3D shape editing methods.

<span style="color: #B330B3;">In parallel, I have begun to explore the application of AI to regional and country studies, in collaboration with Prof. Xiangrong Zhang at Northwest University.</span>

My current research focuses on:
- Text- and image-guided 3D shape editing
- 3D shape synthesis based on 3D Gaussian Splatting
- Generative methods for 3D animation
- AI for Regional and Country Studies

<span style="color: #B330B3;">We are continuously seeking motivated undergraduate and master’s students, and warmly welcome applications to join our research group.</span>

## Links

<div class="about-links">

  {% if site.social.google_scholar %}
  <a class="icon-link" href="{{ site.social.google_scholar }}" target="_blank">
    <i class="fa-brands fa-google-scholar"></i>
    <span>Google Scholar</span>
  </a>
  {% endif %}

  {% if site.social.homepage %}
  <a class="icon-link" href="{{ site.social.homepage }}" target="_blank">
    <i class="fa-solid fa-building-columns"></i>
    <span>Homepage</span>
  </a>
  {% endif %}

</div>
