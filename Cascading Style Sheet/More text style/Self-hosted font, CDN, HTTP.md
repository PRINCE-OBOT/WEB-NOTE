On paper, using a self-hosted font should deliver better performance as it eliminates a third-party connection setup. In practice, the performance differences between these two options is less clear cut. For example, the [Web Almanac](https://almanac.httparchive.org/en/2020/fonts#fig-7) found that sites using third-party fonts had a faster render than fonts that used first-party fonts.

If you are considering using self-hosted fonts, confirm that your site uses a [Content Delivery Network (CDN)](https://web.dev/articles/content-delivery-networks) and [HTTP/2](https://web.dev/articles/content-delivery-networks#http2_and_http3). Without use of these technologies, it's much less likely that self-hosted fonts deliver better performance.

>*"This means that although hosting fonts on our own server seems faster, third-party services like Google Fonts often use CDN and HTTP/2, making them faster unless we do the same for our self-hosted fonts. So, it's not just about the source but how the delivery is optimized."

# CDN

**A CDN (Content Delivery Network) is a network of servers located in different parts of the world that store cached copies of static website resources like fonts, images, CSS, and JavaScript. Instead of always pulling these files from your main server (which might be far away), users can load them from the nearest CDN server. This reduces loading time and improves performance.

*Example*

- When you host your website, it’s stored on a server with an IP address — usually in one location (for example, in the U.S.).
- When someone far away (say, in Nigeria) tries to access your site, they have to send a request to that U.S. server, which can take longer.

- A **CDN** doesn't copy your entire website; instead, it copies **static resources** (fonts, images, CSS, JS) and places them on servers around the world.

- *So, when someone in Nigeria visits your site, the request for static files like fonts and images doesn’t have to go to the U.S. server — it goes to a local CDN server nearby, speeding up loading.
- The dynamic content (like real-time user data) still comes from your main server, but static files are served from closer servers.

# HTTP/2


**This is a faster, more modern version of the HTTP protocol that allows multiple files to be sent at the same time over a single connection.

*Example: 

Imagine ordering five items from a shop and the delivery truck makes five trips for each item (HTTP/1.1), versus delivering all five items in one trip (HTTP/2). It reduces delay, making your fonts, CSS, images, and other resources load more quickly.

# Optimising self-hosted font 

When you self-host a font (keep the font file on your own server), you need to make sure the font is as light and fast as possible. Third-party services like Google Fonts already do this for you, but when it’s your own font file, you must handle it.

Two key optimizations are:

1. **WOFF2 Compression** — This is like putting the font file in a super small, efficient zip bag. It makes loading faster but does not block anything; the browser knows how to unzip and use it immediately.
    
2. **Font Subsetting** — This means removing characters (letters, symbols, languages) that your website doesn’t use, to make the file smaller and faster to load.
    

Why CJK is mentioned:

- Fonts that support Chinese, Japanese, and Korean (CJK) languages contain thousands of characters, making the font file huge.
- Removing unnecessary characters (subsetting) in CJK fonts is tricky, because it’s easy to remove something important by mistake.

**In short:**

- Font file size = complexity (how many characters, languages).
- WOFF2 = compression, faster delivery.
- Subsetting = removing unnecessary characters for faster loading.
- CJK fonts are large, and subsetting them is more challenging.
