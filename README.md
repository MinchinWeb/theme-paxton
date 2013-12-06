Paxton for Jekyll Bootstrap
==========================

*Paxton* is a theme for GitHub Pages by [MinchinWeb](http://github.com/minchinweb/theme-paxton).

This version has been designed to support [Jekyll Bootstrap](http://jekyllbootstrap.com/).

[![](http://minchin.ca/theme-paxton/images/paxton-example.png)](http://minchin.ca/theme-paxton)

## Installation

I'll assume that you already have Ruby up and running. Sorry, that's beyond this
readme.

I'll also assume that you have Jekyll installed. If not, [this page](http://jekyllbootstrap.com/usage/jekyll-quick-start.html) on the Jekyll
bootstrap site will lead you through step-by-step.

Next, you'll need to install the theme. Here's the terminal command:

~~~
$ rake theme:install git="https://github.com/MinchinWeb/theme-paxton.git"
~~~

It should ask you at the end if you want to select the newly installed theme;
hit yes!

## Features

The *Paxton* theme supports three special layouts, in addition to the normal
`pages` and `posts` layouts. To use specify the layout, in the YAML at the top
of post/page, specify it. For example:

~~~yaml
---
layout: redirect
title: Blog
group: nav
redirect_url: http://myblog.example.com
---
~~~

### Landing

This is originally designed as the 'landing page' or the first page you see when
you enter the site.

Whatever you set the title to in the YAML at the top of your page will be
displayed in the lower left.

The rest of the page can be blank.

Use (`index.md`):
~~~yaml
---
layout: landing
title: MinchinWeb
---

~~~

### Contact

This page displays you contact information, or where you can be found around the
web.

To get this to work you need two pieces. First in your site's `_config.yml`, set:

~~~yaml
author :
  name :
  email :
  github :
  twitter :
  feedburner :
  facebook :
  flickr :
  yelp :
  pinterest :
  linkedin :
  google_plus :
~~~

Any ones that are left blank will be skipped.

Next create your contact page (`contact.md`):

~~~yaml
---
layout: contact
title: Contact
---

What ever you write here will show up under
your contact details.
~~~

### Redirect

If for some reason you want a redirect, use this. I created it to link to my
blog which was hosted elsewhere. If Javascript is enabled, you'll be
automatically redirected. Otherwise, the page presents a link for you to click
on.

To use this, make use you specify the redirect URL in the YAML. For exmaple
(`redirect.md`):

~~~yaml
---
layout: rediret
title: Go Away
redirect_url: www.somewhere-else.com
---
~~~

## Customization

### Navigation Bar

If you want a page to show up in the top navigation bar, just add it to the
`nav` group in the top YAML of that page. For example:

~~~
---
layout: page
title: My Cool Page
group: nav
---
~~~

'Home' will always show up on the nav bar.

### Background

The background is intended to fill the browser. However, the theme is designed
to load a smaller image on smaller screens. So create your background image in
the following sizes (in pixels):

* 290x193
* 480x320
* 600x400
* 900x600
* 1350x900
* 1875x1250
* 2550x1700
* 3450x2300
* 4272x2848

They need to go in the following folder:

<pre>(site root)
 `- assets
   `- themes
     `- paxton
	   `- img
	     |- background-290.jpg
		 |- background-480.jpg
		 |- background-600.jpg
		 |- background-900.jpg
		 |- background-1350.jpg
		 |- background-1875.jpg
		 |- background-2550.jpg
		 |- background-3450.jpg
		 `- background-4272.jpg</pre>

If you want to use a different sizes, the code to edit is found in `default.html`.

### Fonts

The theme is set up to use
[Open Sans Condensed](https://www.google.com/fonts/specimen/Open+Sans+Condensed)
and [Life Savers](https://www.google.com/fonts/specimen/Life+Savers), both
courtesy of Google Fonts. If you want to change fonts, you'll need to make
changes in two places:

`(site root)\_layout\default.html` - at the top of the page, you will find the stylesheet that
imports the fonts from Google. Replace this line:

~~~html
<link href='http://fonts.googleapis.com/css?family=Open+Sans+Condensed:300,300italic,700|Life+Savers' rel='stylesheet' type='text/css'>
~~~

`(site root)\assets\themes\paxton\css\paxton.css` - at the top of the file,
you can change which fonts are actually used. Update these lines with your new
font:

~~~css
/* Fonts */
body {
	font-family: 'Open Sans Condensed', sans-serif;
}
h1, h2, h3, h4, h5, h6 {
    font-family: 'Life Savers', cursive;
}
/* End Fonts */
~~~

## License

The Paxton theme is Copyright &copy; 2013 William Minchin.

Permission is granted to you to use, copy, modify, merge, publish, distribute,
sublincense, and/or sell this software, and provide these rights to others,
provided:

    + The above copyright notice and this permission notice shall be included
        in all copies or substantial portions of the software.
    + Attribution is provided in the normal place for recognition of 3rd party
        contributions.
    + You accept that this software is provided to you "as is", without
        warranty.
