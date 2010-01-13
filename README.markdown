I don't like what I see at the URL /collections, how do I change that?
======================================================================

__Answer__

Use CSS. CSS is a powerful tool that can transform the look and feel - and layout - of any web page.

For most, a few CSS rules will do the trick.

When this answer is not satisfying...

_What if CSS is not enough?_

Where is the template for this /collections page? Can't find it. I need to change the HTML. Help!

__Answer__

Fair enough. Read on if you have Liquid skills.

The template that displays the list of collections at /collections is hiding behind the scenes, but we can still pull at it. But first, let's get something out of the way: 

A standard Shopify theme already comes with a handful of Liquid templates. The ability to create alternate templates and snippets guards Shopify themes from getting overbloated over time. Please keep this in mind and be understanding: we may not want yet another template. Bloated anything is not something we affectionate at Jaded Pixel.

We can use the snippet feature to control the markup of our collection listing shown at /collections.

1. Create a new snippet on the Theme Editor page. Call it collection-listing.

2. In it, use the global 'collections' object to generate your own collection listing. To get you started, you can use the file collection-listing.html. Copy its content and paste it inside your collection-listing snippet.

3. Now, open theme.liquid and look for this code:

    {{ content_for_layout }}

4. Replace that code with this:

    {% if template == 'list-collections' %}
    {% include 'collection-listing' %}
    {% else %}
    {{ content_for_layout }}
    {% endif %}

5. Save.

Now visit the page at store.myshopify.com/collections. What you see there in the main content area is entirely controlled by your collection-listing Liquid snippet.