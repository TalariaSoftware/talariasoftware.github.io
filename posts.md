---
layout: default
---

<section class="usa-graphic-list usa-section usa-section--light">
  <div class="grid-container">
    <h1>Posts</h1>
    <div class="usa-graphic-list__row grid-row grid-gap-6">

      {% for post in site.posts %}
        <a href="{{ post.url }}" class='usa-media-block tablet:grid-col-6 padding-3'>
          <i class='fas fa-pen-nib usa-media-block__img font-sans-3xl'></i>
          <div class='usa-media-block__body'>
            <h2 class='usa-graphic-list__heading'>
              {{ post.title }}
            </h2>

            <p>{{ post.description }}</p>
            <p>{{ post.date | date_to_string: "ordinal", "US" }}</p>
          </div>
        </a>
      {% endfor %}
    </div>
  </div>
</section>
