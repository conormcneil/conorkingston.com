---
layout: default
title: Home
---

<main class="container pb-3">
  <div class="row">
    <div class="col-12 col-md-8">
      <section id="case-studies">
        <h2 class="">Project Case Studies</h2>
        {% for case in site.case_studies | limit: 2 %}
          {% unless case.exclude_from_list %}
            {% include card-link.html
              url=case.url
              title=case.title
              date=case.date
              text=case.summary
            %}
          {% endunless %}
        {% endfor %}
        <a href="/case_studies/" class="btn btn-secondary">See More Case Studies</a>
      </section>

      <section id="blog">
        <h2 class="mt-4">Blog</h2>
        <p>stay tuned for more!</P>
        <!-- {% for post in site.posts | limit: 2 %}
          {% unless post.exclue_from_list %}
            {% include card-link.html
              url=post.url
              title=post.title
              date=post.date
              text=post.summary
            %}
          {% endunless %}
        {% endfor %}
        <a href="/blog/" class="btn btn-secondary">See More Blog Posts</a> -->
      </section>
    </div>

    <div class="col-12 col-md-4 mt-5">
      <div class="d-flex justify-content-end mb-3">
        <section class="t">
          <a href="assets/Conor_Kingston_Resume.pdf" class="btn btn-primary">view my resume</a>
        </section>
      </div>
      <section id="contact-me">
        <h2 class="mb-4">Contact Me</h2>
        <form action="https://formspree.io/f/mwpngnrj" method="POST">
          <div class="mb-3">
            <label for="name" class="form-label">Name</label>
            <input type="text" class="form-control" id="name" name="name" placeholder="Your name">
          </div>
          <div class="mb-3">
            <label for="email" class="form-label">Email</label>
            <input type="email" class="form-control" id="email" name="email" placeholder="you@example.com">
          </div>
          <div class="mb-3">
            <label for="message" class="form-label">Message</label>
            <textarea class="form-control" id="message" name="message" rows="4" placeholder="Your message"></textarea>
          </div>
          <button type="submit" class="btn btn-success">Send Message</button>
        </form>
      </section>
    </div>
  </div>
</main>