Don't like what I see at /collections, how do I change that?

Answer:

Use CSS. CSS is a powerful tool that can transform the look and feel - and layout - of a page.
For most, extra CSS rules will do the trick.

One more question:

What if CSS is not enough? Where is the template for this /collections page? Can't find it. I need to change the HTML. Help!

Fair enough. Read on if you have some Liquid skills.

The template that displays the list of collections at /collections is hiding behind the scenes, but we can still pull at it. But first, let's get something out of the way: 

-- a standard Shopify theme already comes with a handful of Liquid templates. The ability to create alternate templates and snippets guards Shopify themes from getting overbloated over time. Please keep this in mind and be understanding. We may not want yet another template. Bloated anything is not something we affectionate at Jaded Pixel --

We can use the snippet feature to control the markup of our collection listing shown at /collections.

1. Create a new snippet on the Theme editor page. Call it collection-listing.liquid. 

2. In it, use the global 'collections' object to come up with your own listing. To get you started, you can use this code stored on github:

3. Now, open theme.liquid and look for this code:

{{ content_for_layout }}

4. Replace that code with this:

{% if template == 'list-collections' %}
{% include 'collection-listing' %}
{% else %}
{{ content_for_layout }}
{% endif %}

5. Save.

Now visit the page at store.myshopify.com/collections. What you see there in the main content area is entirely controlled by your Liquid snippet.