# Webview-caching
Pre-packed content and other strategies for webview [caching](http://tutorials.jenkov.com/android/android-web-apps-using-android-webview.html#caching-web-resources-in-the-android-device).

 I think the key is that as long as css/js are versioned (which every sane web team does) we can safely cache a version on phone without worrying about uncaching it. we should pre-pack only resources like CSS/js and not actual HTML and when it makes a network call it will just load these resources from the cache automatically (you can still cache HTML based on HTTP caching. Also, check Arun's sample

FYI - this is how [CDN](https://css-tricks.com/adding-a-cdn-to-your-website/) works. You put a versioned CSS/js bundle on CDN. HTML is fetched from your application server but CSS/JS/ICONS/any other resources aren't. At Amazon, we used to update the CSS on CDN weekly and after updating used to deploy the new version of website referencing to a new version of CSS.

The structure of webpage also affects a lot. Mostly CSS is loaded in the header and JS in the footer. Cached CSS is much more valuable than JS.
