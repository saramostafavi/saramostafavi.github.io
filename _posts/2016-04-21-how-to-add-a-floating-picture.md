---
layout: post
title:  How to add a floating picture as an alternative to page frontmatter
date:   2016-04-21
---

There are two ways to add a picture to the news item:

1. in the page's [front matter][], add "image: *url*". This makes the
   page use a split layout where the image takes roughly a third of
   the available space on the left, and the text the remaining two
   thirds. (The title and dataline is always above everything.) See
   the preceding three news item for an example of this approach.

2. Leave out "image:" element from the front matter. The news item
   then doesn't use a split layout and the text uses the entire width
   given to it. You can still insert an image with an HTML `<img>` tag
   before a paragraph where you want it to appear. Include in the tag
   a `style="float: left;` attribute, optionally also with a `height`
   and/or `width`. The paragraph will wrap around the image if it's
   longer than the image's height. Like this: 

<img alt="WeBWorKiR question"
src="http://asda.stat.ubc.ca/images/webworkir.png" style="float:
right; height: 400px" />

> Our submission on "Web-based automated
personalized homework with WebWork and R" has been accepted as a
poster for the useR! conference.

Note that most of the time you'll want to put the image at the very
beginning of the article, like
[this](http://asda.stat.ubc.ca/2016/04/06/webworkir-at-user2016.html),
so that it can line up with the start of the text. The source for that
article is:

    ---
    layout: post
    title:  "Learn about WeBWorKiR at useR 2016!"
    date:   2016-04-06
    ---

    <img alt="WeBWorKiR question" src="{{'/images/webworkir.png' | prepend: site.baseurl }}" style="float: right; height: 400px" />
    Our submission on "Web-based automated personalized homework with
    WebWork and R" has been accepted as a poster for the useR! conference.
    ...

[front matter]: https://jekyllrb.com/docs/frontmatter/
