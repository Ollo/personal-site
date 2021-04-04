---
title: How to track adwords conversions on click with Jquery
tags:
  - blog
  - business
  - google analytics
  - jquery
date: 2012-08-28 17:43:08
---

A challenge I've found with conversion tracking is that it requires a user to visit a specific page with conversion tracking code installed in order to register as a conversion ie a landing page. This doesn't always work and makes it difficult to track different forms of conversion such as clicks to third party sites. When faced with this scenario for a client I had to find a solution to track a conversion based on click from an ad. Below is the method and code used to do this using jquery , Google adwords and some html.

First create an html file with your campaigns conversion tracking code from google adwords and add it to your site files.

    <html>
    <body>
        <!-- Google Code for Conversion Page -->
        <script type="text/javascript">
        /* <![CDATA[ */
        var google_conversion_id = xxxxxxxxx;
        var google_conversion_language = "en";
        var google_conversion_format = "3";
        var google_conversion_color = "ffffff";
        var google_conversion_label = "_ArfCLPt9QMQrcfZ2AM";
        var google_conversion_value = 0;
        /* ]]> */
        </script>
        <script type="text/javascript" src="http://www.googleadservices.com/pagead/conversion.js">
        </script>
        <noscript>
        <div style="display:inline;">
        <img height="1" width="1" style="border-style:none;" alt="" src="http://www.googleadservices.com/pagead/conversion/xxxxxxxxx/?label=_ArfCLPt9QMQrcfZ2AM&amp;amp;guid=ON&amp;amp;script=0"/>
        </div>
        </noscript>

        <script type="text/javascript">

          var _gaq = _gaq || [];
          _gaq.push(['_setAccount', 'UA-xxxxxxxx-1']);
          _gaq.push(['_setDomainName', 'yourdomain.com']);
          _gaq.push(['_trackPageview']);

          (function() {
            var ga = document.createElement('script'); ga.type = 'text/javascript'; ga.async = true;
            ga.src = ('https:' == document.location.protocol ? 'https://ssl' : 'http://www') + '.google-analytics.com/ga.js';
            var s = document.getElementsByTagName('script')[0]; s.parentNode.insertBefore(ga, s);
          })();

        </script>
    </body>
    </html>


Next add a class to the links or elements you want to track as conversions via click. I added

`.clickAction` to various buttons and links around the page. Now to create the action add the code below to your header or external js file inside of your document ready function. This script requires [Jquery](http://jquery.com) So you will need to have that also installed on your site.
**note: I wrote this for a WordPress site so update the url path to the html file based on your configuration **

    $('.clickAction').click(function(){

      $('<iframe id="converter" height="1" width="1" name="converter">').attr('src', <?php bloginfo('template_url'); ?>/tracking.html').appendTo('body');

    });

Now any item with the class `.clickAction` when clicked with load a 1px by 1px transparent iframe at the bottom of the page and register as a conversion. This approach is pretty simple so feel free to reach out if you have questions. Happy analyzing.
