.. _Enabling A CDN For Course Assets:

######################################
Enabling A CDN For Course Assets
######################################

.. note: Depending on your courseware, you may not need a CDN.  Not all
 installations are alike, and this will need to be a decision based on the
 type, and amount, of content in your courses.

When courses has asset, those course assets are served directly from the edX
instance. For popular courses, or courses with large assets -- high-quality
images, PDFs, video -- this can increase not only the load on the instance
but also the time it takes to load these courses.

You can configure your edX instance to instead serve these assets through a CDN,
which offloads the work required to deliver them from the edX instance.

A CDN, or content delivery network, is a service that places servers all around
the world, and keeps copies of content on those servers. Instead of serving the
files from one location, it serves them from whichever server is closest to the
end user. This provides faster download speeds and, ultimately, faster page
loads.

For your CDN, you should point it to your edX instance as the origin server.
Cache expiration should be chosen carefully: you want content to be cached long
enough to keep the load on your edX instance low, but not so long that you can’t
upload changes to assets and have them realized in a reasonable amount of time.
A good starting point is one hour.

Once your CDN is configured, follow these steps.

#. Sign in to the Django administration console for your base URL. For example,
   ``http://{your_URL}/admin``.

#. In the **Static_Replace** section, next to **Asset base url configs** select
   **Add**.

#. Select **Enabled**.

#. Enter the hostname for your CDN provider.

   For example, if you were using CloudFront, this would look something like
   `d37djvu3ytnwxt.cloudfront.net`. Be sure not to include the scheme
   (*http://* or *https://*) when specifying the hostname.

#. Select **Save** at the bottom of the page.


.. include: ../../../../links/links.rst
