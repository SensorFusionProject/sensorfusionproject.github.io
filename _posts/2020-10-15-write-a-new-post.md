---
layout: post
current: post
cover: assets/images/cover/writing.jpg
navigation: True
title: 포스팅 하는 법
tags: [getting-started, blog]
class: post-template
subclass: 'post'
author: coolwind
---

## Naming and Path

Create a new file named `YYYY-MM-DD-TITLE.EXTENSION` and put it in the `_posts/` of the root directory. Please note that the `EXTENSION` must be one of `md` and `markdown`. From `v2.4.1`, you can create sub-directories under `_posts/` to categorize posts.

## Front Matter

Basically, you need to fill the [Front Matter](https://jekyllrb.com/docs/front-matter/) as below at the top of the post:

```yaml
layout: post
current: post
cover: assets/images/cover/whatever_in_the_cover_folder.jpg
navigation: True
title: your_title
date: YYYY-MM-DD HH:MM:SS +/-TTTT
tags: [tag1, tag2]     # TAG names should always be lowercase
class: post-template
subclass: 'post'
author: your_nickname
```

> **Note**: The posts' ***layout*** has been set to `post` by default, so there is no need to add the variable ***layout*** in Front Matter block.

### Timezone of date

In order to accurately record the release date of a post, you should not only setup the `timezone` of `_config.yml` but also provide the the post's timezone in field `date` of its Front Matter block. Format: `+/-TTTT`, e.g. `+0800`.

### Tags

The number of elements in `tags` can be zero to infinity.

The list of posts belonging to the same _tag_ is recorded on a separate page. At the same time, the number of these _tag_ type pages is equal to the number of `tags` elements for all posts, which means that the two number must be exactly the same.

For instance, let's say there is a post with front matter:

```yaml
tags: [bee, pig]
```

Then we should have two _tag_ type pages placed in folder `tags`  of root:

```sh
.
├── tags
│   └── bee.html            # a tag type page
│   └── pig.html            # a tag type page
...
```

the content of a _tag_ type page is

```yaml
---
layout: tag
title: TAG_NAME             # e.g. bee
tag: TAG_NAME               # e.g. bee
---
```

With the increasing number of posts, the number of tags will increase several times!  If we still manually create these _tag_ type files, it will obviously be a super time-consuming job, and it is very likely to miss some of them, i.e., when you click on the missing `tag` link from a post or somewhere, the browser will complain to you "404 Not Found".

## Comments

Similar to TOC, the [Disqus](https://disqus.com/) comments is loaded by default in each post, and the global switch is defined by variable `comments` in file `_config.yml` . If you want to close the comment for specific post, add the following to the **Front Matter** of the post:

```yaml
---
comments: false
---
```


## Mathematics

For website performance reasons, the mathematical feature won't be loaded by default. But it can be enabled by:

```yaml
---
math: true
---
```


## Pinned Posts

You can pin one or more posts to the top of the home page, and the fixed posts are sorted in reverse order according to their release date. Enable by:

```yaml
---
pin: true
---
```

## Code Block

Markdown symbols <code class="highlighter-rouge">```</code> can easily create a code block as following examples.

```
This is a common code snippet, without syntax highlight and line number.
```

## Specific Language

Using <code class="highlighter-rouge">```language</code> you will get code snippets with line Numbers and syntax highlight.

> **Note**: The Jekyll style `{% raw %}{%{% endraw %} highlight LANGUAGE {% raw %}%}{% endraw %}` or `{% raw %}{%{% endraw %} highlight LANGUAGE linenos {% raw %}%}{% endraw %}` are not allowed to be used in this theme !

```yaml
# Yaml code snippet
items:
    - part_no:   A4786
      descrip:   Water Bucket (Filled)
      price:     1.47
      quantity:  4
```

#### Liquid Codes

If you want to display the **Liquid** snippet, surround the liquid code with `{% raw %}{%{% endraw %} raw {%raw%}%}{%endraw%}` and `{% raw %}{%{% endraw %} endraw {%raw%}%}{%endraw%}` .

{% raw %}
```liquid
{% if product.title contains 'Pack' %}
  This product's title contains the word Pack.
{% endif %}
```
{% endraw %}


## Learn More

For more knowledge about Jekyll posts, visit the [Jekyll Docs: Posts](https://jekyllrb.com/docs/posts/).

