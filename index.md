---
layout: default
hero:
  image: /images/hero.png
  callout: Start for Free
  button:
    href: https://app.talariasoftware.com/expertise_to_income
    text: Get the FREE Workbook
  link:
    text: Link to more about that priority
    href: /link/
  content: |
    Software businesses generate wealth and passive income.

    This FREE workbook will help you get started on yours today.
---

<section class="usa-graphic-list usa-section usa-section--light">
  <div class="grid-container">
    <h1>I want to …</h1>
    <div class="usa-graphic-list__row grid-row grid-gap">
      <div class="usa-media-block tablet:grid-col">
        <i class="far fa-lightbulb usa-media-block__img font-sans-3xl"></i>
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">Kickstart My Idea</h2>
          <p>I have an idea and a dream to turn that idea into a product and business.</p>
          <p>I am ready to make that dream into a reality, to build my product, build my business, and build my new life.</p>
          <a class="usa-button usa-button--secondary" href="https://app.talariasoftware.com/kickoff_questionnaires/new">Get Started </a>
        </div>
      </div>
      <div class="usa-media-block tablet:grid-col">
        <i class="fas fa-chart-line usa-media-block__img font-sans-3xl"></i>
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">Accelerate My Team</h2>
          <p>I have a product in development but making improvements and changes is slow or expensive and when I finally do get them it turns out they are not what my customers need.</p>
          <p>I am ready to make a change so I can quickly and efficiently deliver what my customers want.</p>
          <a class="usa-button usa-button--secondary" href="https://app.talariasoftware.com/accelerate_questionnaires/new">Level Up</a>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="usa-graphic-list usa-section usa-section--dark">
  <div class="grid-container">
    <h1>Recent Articles</h1>
    <div class="usa-graphic-list__row grid-row grid-gap-6">

      {% for post in site.posts limit: 4 %}
        <a href="{{ post.url }}" class='usa-media-block tablet:grid-col-6 padding-3'>

          {% if post.layout == 'facebook_video' %}
            <i class='fab fa-youtube usa-media-block__img font-sans-3xl'></i>
          {% elsif post.layout == 'youtube' %}
            <i class='fab fa-youtube usa-media-block__img font-sans-3xl'></i>
          {% elsif post.layout == 'fireside_fm' %}
            <i class='fas fa-microphone-alt usa-media-block__img font-sans-3xl'></i>
          {% elsif post.layout == 'anchor_fm' %}
            <i class='fas fa-microphone-alt usa-media-block__img font-sans-3xl'></i>
          {% else %}
            <i class='fas fa-pen-nib usa-media-block__img font-sans-3xl'></i>
          {% endif %}

          <div class='usa-media-block__body'>
            <h2 class='usa-graphic-list__heading'>
              {{ post.title }}
            </h2>

            <p>{{ post.description }}</p>
            <p>{{ post.date | date_to_string: "ordinal", "US" }}</p>
          </div>
        </a>
      {% endfor %}
      <a class="usa-button usa-button--secondary margin-x-auto" href="/articles">All Articles</a>
    </div>
  </div>
</section>

<section class="usa-section usa-section--light">
  <div class="grid-container">
    <div class="grid-row grid-gap">
      <div class="tablet:grid-col-4">
        <img class="height-15" src="/images/foot-color.png" alt='logo' />
        <h2 class="text-primary font-heading-lg margin-top-0 tablet:margin-bottom-0">
          Build Software.
        </h2>
        <h2 class="text-secondary font-heading-lg text-light text-uppercase margin-top-0 tablet:margin-bottom-0">
          Delight Customers.
        </h2>
      </div>
      <div class="tablet:grid-col-8 usa-prose">
        <p>Software is a means to an end. Your real goals are to delight your customers, grow your business, and make people's lives better. Building software is only valuable when it helps you do those things.</p>
        <p>In order to do that you need to your software to adapt quickly to changes in your environment and in your understanding. And you need to do that in a way that is sustainable because you are in this for the long haul.</p>
      </div>
    </div>
  </div>
</section>
<section class="usa-graphic-list usa-section usa-section--dark">
  <div class="grid-container">
    <div class="usa-graphic-list__row grid-row grid-gap">
      <div class="usa-media-block tablet:grid-col">
        <i class="fas fa-clock usa-media-block__img font-sans-3xl"></i>
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">Build Quickly</h2>
          <p>Develop your products rapidly in order to get to market faster and find product-market fit sooner.</p>
        </div>
      </div>
      <div class="usa-media-block tablet:grid-col">
        <i class="fas fa-money-bill usa-media-block__img font-sans-3xl"></i>
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">Build Efficiently</h2>
          <p>Save time and money with sustainable practices that ensure you can keep moving forward at a steady pace.</p>
        </div>
      </div>
      <div class="usa-media-block tablet:grid-col">
        <i class="fas fa-laugh-beam usa-media-block__img font-sans-3xl"></i>
        <div class="usa-media-block__body">
          <h2 class="usa-graphic-list__heading">Delight Customers</h2>
          <p>Create products that your customers will love through continual, sustainable feedback and adjustment.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<section class="usa-section usa-section--light">
  <div class="grid-container">
    <div class="grid-row grid-gap flex-align-center">
      <div class="tablet:grid-col-4">
        <h1>Get Your Free Workbook Today</h1>
        <p class="measure-1">
          This step-by-step workbook for entreprenuers of all experience-levels and types. At the end of these 46-pages you'll have a plan laid out and will have already taken the first steps.
        </p>
        <a class="usa-button usa-button--secondary width-full margin-bottom-2" href="https://app.talariasoftware.com/expertise_to_income">Download Now </a>
      </div>
      <div class="tablet:grid-col-8 text-center">
        <h1>
          <img class="height-card-lg" alt="Turn Your Expertise Into Passive
          Income" src="/images/expertise_to_income_cover.png" />
        </h1>
      </div>
    </div>
  </div>
</section>

