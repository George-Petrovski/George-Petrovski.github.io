---
title: Blog History
subtitle: Blog Renewal
layout: post_detail
date-created: 2021-05-27
date-edited: [2021-06-06, 2021-06-21]
img: dreams.png
thumbnail: 2021-05-27-blog-history-thumbnail.jpg
alt: image-alt
category: [Post, Blog]
description: Blog History
comments: true
---

### Blog History

#### Blog Renewal
* Date: 2021-06-06
* Basic Theme: Agency Jekyll Blog Theme
* Source: [agency-jekyll-theme](https://github.com/raviriley/agency-jekyll-theme)

#### Configure Blog
* Date: 2021-05-27
* Details: Change BaseURL, Theme

#### Set Up Local Environment
* Date: 2021-05-28
* Stack: Docker, Git
* Reference: [Docker Local Envrionment](https://jehuipark.github.io/blog/blog-env-setting-with-docker)
* docker-compose.yml code: 
```Go
version: "3.3"
services:
  jekyll:
    image: jekyll/jekyll:latest
    command: jekyll serve --force_polling --drafts --livereload --trace
    ports:
      - "4000:4000"
    volumes:
      - ".:/srv/jekyll"
```
* Reference: [Docker Local Environment .yml file](https://www.44bits.io/ko/post/almost-perfect-development-environment-with-docker-and-docker-compose)

#### Add Typed Animation in Header Introduction
* Date: 2021-05-28
* Stack: Liquid, Javascript(typed.min.js)
* Code:
```Javascript
<script type="text/javascript">
                    var typed = new Typed('.typed', {
                        // Waits 1000ms after typing "First"
                        strings: [
                            'Developer.',
                            'Always Student.'
                        ],
                        smartBackspace: true,
                        typeSpeed: 30,
                        backSpeed: 30,
                        backDelay: 1000,
                        loop: true,
                        loopCount: Infinity
                    });
                </script>
```
* Result:
![Typed Animation]({{ site.url }}/img/post/blog/blog-history/header-typed-animation.gif "Logo Title Text 1")

#### Add Social
* Date: 2021-05-29
* Stack: Liquid, Jekyll
* Details: StackOverFlow, Github, Linkedin

#### Fix Nav Menu Shrink Error
* Date: 2021-05-29
* Stack: Liquid, Jekyll, Javascript, jQuery
* Problem: Nav Bar doesn't shrink when scroll down.
* Cause: In default.html, js.html is moved to the top second position for typed animation.
* Solution: In header.html, typed animation script tags is surrounded by document.
* Code:
```Javascript
document.addEventListener("DOMContentLoaded", function(event) { });
```

#### Fix Mail Error
* Date: 2021-05-29
* Stack: Liquid, Jekyll, Javascript, HTML, ajax
* Problem1: Mail Service doesn't work.
* Cause: Github pages Service only supports static websites, not dynamic website(node.js, php, and etc).
* Solution: Use formspree.io service.
* Details:
1. The ‘agency Jekyll theme’ mail service is made by php which is server-side programming language. However, Github pages only supports static html components, so a blog that is serviced by Github pages cannot actually run server side components including node.js, php…. I’ll use formspree.io service
Formspree.io service only takes json file with special header.
2. Using Ajax with Formspree.io
* Problem2
1. Form name missing
2. Redirect Page missing
* Solution
1. Add name for each input
2. Modify url, method, dataType data
(Formspree only accept json => CORS policy)
```Javascript
$.ajax({
  url: "https://formspree.io/f/YOUR_FORM_ID",
  method: "POST",
  dataType: "json",
  data: {
    email: "a.visitor@email.com",
    message: "Hello!"
  }
});
```

* Reference:
1. [https://dev.to/charalambosioannou/create-a-static-webpage-with-a-contact-form-on-github-pages-3532](https://dev.to/charalambosioannou/create-a-static-webpage-with-a-contact-form-on-github-pages-3532)
2. [https://dev-yakuza.posstree.com/ko/jekyll/send-email/](https://dev-yakuza.posstree.com/ko/jekyll/send-email/)
3. [https://stackoverflow.com/questions/24348223/send-email-from-static-page-hosted-on-github-pages](https://stackoverflow.com/questions/24348223/send-email-from-static-page-hosted-on-github-pages)
4. [https://jehwanyoo.net/2020/09/28/%EC%A0%95%EC%A0%81-%EC%82%AC%EC%9D%B4%ED%8A%B8(Github%20Pages)%EC%97%90%EC%84%9C-%EC%B5%9C%EC%8B%A0%EA%B8%80-%EB%B6%88%EB%9F%AC%EC%98%A4%EA%B8%B0-%EA%B8%B0%EB%8A%A5-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0/](https://jehwanyoo.net/2020/09/28/%EC%A0%95%EC%A0%81-%EC%82%AC%EC%9D%B4%ED%8A%B8(Github%20Pages)%EC%97%90%EC%84%9C-%EC%B5%9C%EC%8B%A0%EA%B8%80-%EB%B6%88%EB%9F%AC%EC%98%A4%EA%B8%B0-%EA%B8%B0%EB%8A%A5-%EA%B5%AC%ED%98%84%ED%95%98%EA%B8%B0/)
5. [https://help.formspree.io/hc/en-us/articles/360013470814-Submit-forms-with-JavaScript-AJAX-](https://help.formspree.io/hc/en-us/articles/360013470814-Submit-forms-with-JavaScript-AJAX-)


#### Add Favicon
* Date: 2021-05-31
* Stack: Liquid, Jekyll, Javascript, HTML

#### Add Biography
* Date: 2021-05-31
* Stack: Liquid, Jekyll, Javascript, HTML
* Details: Agency Jekyll Theme had about section, but I replace it with biography section

#### Write Short About
* Date: 2021-06-01
* Stack: Liquid, Jekyll, Javascript, HTML
* Details: Modify About Description

#### Add Resume Button
* Date: 2021-06-01
* Stack: Liquid, Jekyll, Javascript, HTML
* Details: Add Resume Button in about section

#### Fix Font Size Error
* Date: 2021-06-02
* Stack: Liquid, Jekyll, Javascript, HTML
* Details:
  * Add custom.css for responsive css
  * Add in style tag
{% raw %}
{% include css/custom.css %}
{% endraw %}
 
#### Seperate Post and Portfolio
* Date: 2021-06-05
* Stack: Liquid, Jekyll, Javascript, HTML
* Details:
  1. Using Jekyll Default Function "Category"
  2. Add Category to Markdown File (e.g. Post, Portfolio)

#### Seperate default.html and index.html
* Date: 2021-06-05
* Stack: Liquid, Jekyll, Javascript, HTML
* Details:
  1. Seperate default template and index.html for the purpose for Scalable Static Website

#### Create post_grid.html
* Date: 2021-06-05
* Stack: Liquid, Jekyll, Javascript, HTML
* Details:
  1. Create post_grid.html
  2. Add Liquid If statement to Filter Post only
```
{% for post in site.posts %}
{% if post.category == "Post" %}
{% endif %}
{% endfor %}
```

#### Update custom.css
* Date: 2021-06-05
* Stack: Liquid, Jekyll, Javascript, HTML
* Details:
  1. Modify custom.css for style for post
  2. Change portfolio style to post style

#### Fix Hover Color Error
* Date: 2021-06-05
* Stack: Liquid, Jekyll, Javascript, HTML
* Details:
  1. Modify agency.css
  2. Modify custom.css
  3. Modify rgba

#### Add Tell me more button in portfolio and post section
* Date: 2021-06-05
* Stack: Liquid, Jekyll, Javascript, HTML

#### Seperate nav and header
* Date: 2021-06-05
* Stack: Liquid, Jekyll, Javascript, HTML

#### Change Nav background from transparent to #222
* Date: 2021-06-05
* Stack: Liquid, Jekyll, Javascript, HTML

#### Create nav_home and nav_detail
* Date: 2021-06-05
* Details:
1. Seperate nav.html into nav_home and nav_detail for detailed homepage

#### Modify layout
* Date: 2021-06-05
* Details:
  1. Modify layout default
  2. Create layout detail

#### Create Detail pages
* Date: 2021-06-05
* Details:

#### Fix Recent Portfolio and Post Limit Error
* Date: 2021-06-05
* Details:
1. Use assign statement to filter only portfolios from posts.
2. Limit show only 6 Portfolios
3. Use assign statement to filter only posts from all posts + portfolios.
4. Limit show only 6 Posts

#### Fix Margin right Error
* Date: 2021-06-06
* Problem: Contents doesn't fit to the full width in Mobile Environment(width:360px)
* Cause: Using <div class="row"> inside a div with row class

#### Change Post Markdown Layout
* Date: 2021-06-06
1. Change Post Markdown Layout from default to detail
* Purpose: Generate Links in Detail Homepage

#### Focusing on Posting after...
* Date: 2021-06-08

#### Remove Empty Spaces in Grid
* Date: 2021-06-21
* Problem: 2 Empty Spaces after third columns
* Cause: The length of title
* Solve: Modify Grid System from col-md-4 to col-md-6