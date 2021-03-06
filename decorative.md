---
title: "Decorative Images"
permalink: /tutorials/images/decorative/
layout: default
description: 
image: /content-images/wai-tutorial-images/social.png
github:
  repository: w3c/wai-tutorial-images
  path: 'decorative.md'
footer: > # Text in footer in HTML
  
inline_css: |
  .ex, .ap {
    b, &:before {
      color: #005A6A;
      font-weight: inherit;
    }
  }
  .risky {
    &:after {
      background-color: #005A6A;
      color: #fff;
      font-weight: normal;
      border-radius: 100%;
      width: 1.2em;
      height: 1.2em;
      margin-left: .6em;
      line-height: 1.2;
      text-align: center;
      display: inline-block;
      content: "!";
    }
  }
  .ex {
    counter-increment: examples;
    counter-reset: approaches;
  }
    .ex:before {
      content: 'Example ' counter(examples) ': ';
    }
    .ex.inap {
      counter-reset: none;
    }


  .newap {
    counter-reset: approaches;
  }

  .newex {
    counter-reset: examples;
  }


  h2.first, h3.first, .newexap {
    counter-reset: examples approaches;
  }

  .ap {
    counter-increment: approaches;
  }
    .ap:before {
      content: 'Approach ' counter(approaches) ': ';
    }
wcag_techniques:
- H2
- H67
---

{::nomarkdown}
{% include_cached toc.html type="start" title="Page Content" class="full" %}
{:/}

-   TOC is created automatically.
{:toc}

{::nomarkdown}
{% include_cached toc.html type="end" %}
{:/}

Decorative images don’t add information to the content of a page. For example, the information provided by the image might already be given using adjacent text, or the image might be included to make the website more visually attractive.

In these cases, a null (empty) `alt` text should be provided (`alt=""`) so that they can be ignored by assistive technologies, such as screen readers. Text values for these types of images would add audible clutter to screen reader output or could distract users if the topic is different from that in adjacent text. Leaving out the `alt` attribute is also not an option because when it is not provided, some screen readers will announce the file name of the image instead.

Whether to treat an image as decorative or [informative]({{"/tutorials/images/informative/" | relative_url}}) is a judgment that only the author can make, based on the reason for including the image on the page. Images may be decorative when they are:

-   Visual styling such as borders, spacers, and corners;
-   Supplementary to link text to improve its appearance or increase the clickable area;
-   Illustrative of adjacent text but not contributing information (“eye-candy”);
-   Identified and described by surrounding text.

The examples below show how to use the `alt` attribute when decorative images are provided using the `<img>` element. Where possible, decorative images should be provided using CSS background images instead.

## Image used as part of page design
{:.ex}

This image is used as a border in the page design and has a purely
decorative purpose.

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}
{:/}

![]({{ "/content-images/wai-tutorial-images/topinfo_bg.png" | relative_url }})

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<img src="topinfo_bg.png" alt="">
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

Screen readers also allow the use of WAI-ARIA to hide elements by using `role="presentation"`. However, currently, this feature is not as widely supported as using a null `alt` attribute.

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<img src="topinfo_bg.png" role="presentation">
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Note" class="simple note" %}
{:/}

If the image was used to indicate a thematic break, e.g. a scene change in a story, or a transition to another topic, using the `<hr>` element would be appropriate to notify assistive technology.

{::nomarkdown}
{% include box.html type="end" %}
{:/}

## Decorative image as part of a text link
{:.ex}

This illustration of a crocus bulb is used to make the link easier to identify and to increase the clickable area but doesn’t add to the information already provided in the adjacent link text (of the same anchor). In this case, use a null (empty) `alt` value for the image.

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}
{:/}

[![]({{ "/content-images/wai-tutorial-images/crocus.jpg" | relative_url }}){:style="vertical-align: middle; margin-right: 1em;"}**Crocus bulbs**](../beyond.html)

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<a href="crocuspage.html">
  <img src="crocus.jpg" alt="">
  <strong> Crocus bulbs</strong>
</a>
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

## Image with adjacent text alternative
{:.ex}

This picture of a sleeping dog is already sufficiently described by the adjacent text. There is no need to repeat this information, and a null (empty) `alt` value can be used for this image.

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}
{:/}

![]({{ "/content-images/wai-tutorial-images/sleeping.jpg" | relative_url }}){:style="float:left; margin-right: 1em;"} **The sleeping dog:** Let sleeping dogs lie is a proverb that means “don’t initiate trouble. If something that could be troublesome is quiet, then leave it alone”.

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<p>
  <img src="sleepingdog.jpg" alt="">
  <strong>Let sleeping dogs lie:</strong> ...
</p>
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

## Image used for ambiance (eye-candy)
{:.ex}

This image is used only to add ambiance or visual interest to the page.

{::nomarkdown}
{% include box.html type="start" title="Example" class="example" %}
{:/}

![]({{ "/content-images/wai-tutorial-images/kew.jpg" | relative_url }}){:style="float:left; margin-right: 1em;"} Don’t miss the impressive Tropical House – a huge greenhouse that displays examples of exotic plant-life from every tropical environment on the planet.

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Code" class="example" %}
{:/}

~~~ html
<img src="tropical.jpg" alt="">
~~~

{::nomarkdown}
{% include box.html type="end" %}
{:/}

{::nomarkdown}
{% include box.html type="start" title="Note" class="simple note" %}
{:/}

If the purpose of this image was to identify a plant or convey other information, rather than just to improve the look of the page, it should probably be treated as [informative]({{"/tutorials/images/informative/" | relative_url}}). The author determines the purpose for the use of the image.

{::nomarkdown}
{% include box.html type="end" %}
{:/}
