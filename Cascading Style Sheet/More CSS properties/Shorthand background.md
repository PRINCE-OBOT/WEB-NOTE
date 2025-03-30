
# multiple layer

```css

background : <image> <position> / <size> <repeat> <attachment> <origin> <clip>

```


### position && size

>**Note**: 
>1. You cannot provide the `size` without having the `position`

*Example*
```css
background: <image> <size> <repeat> ... ❌
```

>2. You can provide the `position` without having the `size`.

*Example*

```css

background: <image> <position> <repeat> ... ✅

```

>3. If you have to provide both `position` and `size` provide `position` first, followed by `size`and separate then by `/`

*Example*

```css

background: <image> <position> / <size> <repeat> ...
```


### origin && clip

>4. When you provide **just one visual box** in the `background` shorthand, it applies to **both `background-origin` and `background-clip`**


```css

background: url('image.jpg') no-repeat border-box;

```
*Example*
Here, border-box applies to both:

- `background-origin: border-box;`
    
- `background-clip: border-box;`


>5. If you want to specify them differently, then you must give **two visual boxes**:

```css

background: url('image.jpg') no-repeat padding-box content-box;
```


- First one (`padding-box`) is for `background-origin`.
    
- Second one (`content-box`) is for `background-clip`.

### multiple background 

To put multiple background in a single element provide them and separate them by `,`(comma)

*Example*

```css
background: url(./source1), url(./source2.jpg)
```
>**Note** The `source1` display on top over the `source2`.