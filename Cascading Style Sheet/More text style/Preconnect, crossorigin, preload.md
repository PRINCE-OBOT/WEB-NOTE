

```html

head>
  <link rel="preconnect" href="https://fonts.com">
  <link rel="preconnect" href="https://fonts.com" crossorigin>
</head>
```

# preconnect 

>**Preconnect is like telling the browser: 'I will soon request something from fonts.googleapis.com, please prepare the connection now so that when the real request comes, it will be faster and reduce waiting time.'



# Crossorigin


>**The crossorigin attribute tells the browser to request the resource (like a font) as a cross-origin request and allows the server to confirm permission via CORS headers, so the resource can safely be used by my website.



***crossorigin values:

1. **crossorigin="anonymous" (or just crossorigin)**

- The browser makes the request **without sending any cookies or credentials**.
- The third-party server must respond with `Access-Control-Allow-Origin: *` or `Access-Control-Allow-Origin: yourdomain.com` for the resource to be used.
- If the server doesn't allow it, the browser won't use the resource.
- Use this when you don't need private access — like loading fonts or images that are meant to be publicly available.


2. **crossorigin="use-credentials"**

- The browser makes the request **with credentials** (cookies or saved authentication details for that domain).
- The third-party server must respond with `Access-Control-Allow-Credentials: true` and allow your domain.
- Use this when the resource is protected and only available to logged-in or verified users.


## Why do I need to include two link


1. "To ensure the browser prepares a connection to the third-party server in advance, so when the font is requested through the stylesheet, it downloads faster and reduces waiting time."


2. "It tells the browser to treat the font request as cross-origin, allowing the third-party server to confirm permission via CORS headers. Without this, the browser may block the font from being used on the website."


# preload


`preload` is a hint you give to the browser to tell it:

> _"Download this resource (like a font, script, image) as early as possible, because it will be needed soon."_

It reduces waiting time when the browser encounters the resource later in CSS or JS — the file is already downloaded and sitting in cache, ready to go.

Example:

```html
<link rel="preload" href="myfont.woff2" as="font" type="font/woff2" crossorigin="anonymous">
```

The browser pre-downloads `myfont.woff2` and won’t need to wait when it reaches the CSS `@font-face`.


### Disadvantages of `preload`:

1. **Wasted bandwidth if the resource is never used**  
    — If you preload something that ends up not being needed (maybe the text or component doesn't render), you’ve wasted bandwidth.  

    
2. **Can block other important resources**  
    — Preloading too many resources too early can make the browser busy and delay critical ones like CSS or JS.  
    
    
3. **Ignores Unicode-range optimization**  
    — If you preload a font file, it is downloaded fully even if your text doesn’t use all the glyphs.  
    So the `unicode-range` filtering benefit is lost. The browser won't “check text first” — it just downloads the file straight away.  
    Real life: It’s like sending someone to buy all possible ingredients, even if you only end up cooking one dish.
    
4. **Overusing preload leads to performance drops**  
    — Too many preload requests overwhelm the browser and defeat the purpose of optimization.
    

