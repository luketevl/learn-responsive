# learn-responsive
Learning responsive

## LINKS

- http://www.w3.org/TR/css3-mediaqueries/
- http://www.dropboxwiki.com/tips-and-tricks/host-websites-with-dropbox
- https://developer.chrome.com/devtools/docs/remote-debugging
- https://www.npmjs.com/package/weinre
- https://icomoon.io/app/#/select

## MOBILE SITE or RESPONSIVE DESIGNER
> When we talk about mobile, what exactly is mobile?
Let's try to define mobile. When you think about making a mobile site, a mobile page, what separates those devices from others that are not mobile?
Let's think. Was it a small screen? So, having a small screen, does it mean it's a mobile device? Well, if I have a tablet, is not it mobile? That's not quite it, right?
Let's try again. Maybe it's portability. I have a device that I can use anywhere: in the square, on the street. Well, if I take my notebook to the square, would it be mobile? Maybe not.
Let's think. Maybe then it's the mobile networks. The fact that I can access my device through 3G or 4G defines that it is mobile. Well, if I buy that 3G USB plug in computer, am I on a mobile? Yeah, you see. Maybe not.
So let's try another one: touch screen. Perhaps what defines mobile is a touch screen. So, if you have a hybrid computer, with Windows 8, for example, the first touch-enabled computers, you're on a mobile device? Then you think: I do not know. It's difficult.
The big question, in fact, is that there is no mobile. Trying to make this separation between what is and what is not mobile is problematic. There are, of course, the extremes. If you show a smartphone, you'll tell me that it's a mobile; If it shows a big desktop computer, it obviously will not be mobile. But the point is that in the middle between these two devices, there are several possibilities, and they are difficult to define. Sometimes you have a tablet as big as a notebook, but sometimes you have a hybrid notebook that turns tablet. Sometimes you have a touch screen, sometimes not, how could it be that you also have 3G, but also not.
Anyway. The big question is, it does not matter, it does not matter. There is no mobile, so we are not interested in this division. What exists are several different devices with different characteristics and we want our site to support them all.

## RESPONSIVE DESIGNER

### FLUID DESIGNER
- _Think_ in **proportions**
- _Use_ **%** |  **flexible mensure**
  - **%** in **font-size** is **x%** _more_ size than your **parent**
  - For **text** use **em**

#### TECHNIQUES
- **MAX-WIDTH** | Used to _limit_ your _responsive_
```css
parent {
  margin: 0 auto; /* CENTER ELEMENT */
  width: 100%;
  max-width: 1200px; /* Max limit responsive */
}
```
- **MIN-WIDTH** | Used to _limit_ your _responsive_
```css
parent {
  margin: 0 auto; /* CENTER ELEMENT */
  width: 50%;
  min-width: 200px; /* Max limit responsive */
}
```
##### IMAGES RESPONSIVES
> Rename your img with type that **resolution** | nameImg _@_ **resolution** .format

Example: **logo@2x.png**

- **MAX-WIDTH** | _Does not allow_ the image to **exceed its maximum size**
```css
img{
  max-width: 100%;
}
```
- **Change <img />** with _resolution_ using new attribute **SRCSET**
```html
<img src="name.png" srcset="name@2x.png 2x, name.png 1x" />
```

###### SVG
- **Compatibility**
  -  IE8 >
  -  android 3 =>
```html
<img src="logo.svg" onerror="this.src='logo.png'; this.onerror=null" />
```

###### COMPRESSIVE IMAGES
> It's pretty much optimize a full-size image so it's reasonably sized for multiple devices. We reduce image quality, increase compression, use lighter formats, etc.

###### FUTURE
- See _about_
```html
<picture />
```

#### MEDIA QUERIES
- _Do think_ **MOBILE FIRST** | Write css default in **mobile** and add _break points_ in _media queries_ for **desktop**
  - Use **min-width**
- **Condition layout** | _Specify_ the _break points_
- **Syntax**
  - **MAX/min WIDTH/HEIGHT** | _Get_ _browser_ **size**
  - **DEVICE WIDTH/HEIGHT** | _Get_ _screen hardware_ **size**
```css
@media (min-width|max-width|width|device-width|min-height|max-height|height|device-height: size orientation:portrait|landscape){
}
```
- **Syntax** for _old browsers_
```css
@media only screen (min-width|max-width|width|device-width|min-height|max-height|height|device-height: size orientation:portrait|landscape){
}
```
- __Check__ **DPI**
- **Performance**
- **Visual quality**
  - For **legacy** _use_ **-webkit-min-device-pixel-ratio** | It does not have **dppx**
```css
@media (resolution|min-resolution|max-resolution: 1|1.5|2dppx){}
```


#### VIEWPORT
- **Added** **viewport** to _alert mobile_ that your page is _responsive_
```html
<!-- AUTOMATIC MODE RECOMMEND-->
<meta name='viewport' content='width=device-width'>

<!-- MANUAL MODE -->
<meta name='viewport' content='width=320'>
```
- **Viewport** to **iOS** use:
```html
<meta name="viewport" content="width=device-width, initial-scale=1">.
```


## WORKFLOW
- **Desktop browser**
  - Development
  - Productivity
  - Tools
- **Emulators**
  - Compatibility
  - BUGS
  - Variations
  - Differences
  - Low cost
- **Devices**
  - Performance
  - Touch
  - UX
  - Size

## UX MOBILE TIPS
- **Functions focused**
- **Content Prioritization**

### TOUCH FIRST
- _Think_ ever in **touch**
- _Think_ _size_ in **MM** **millimeters**
- **SIZE BUTTONS**
  - _Microsoft_
    - **7mm** = **40px**  | **2mm** _padding_ **10 px** _between_ | **MINIMUM**
    - **9mm** = **50px**  | **2mm** _padding_ **10 px** _between_ | **RECOMMEND**
    - **5 < mm** = **30px**  | **2mm** _padding_ **10 px** _between_ | **IMPOSSIBLE**
- **Don't** _use_ **HOVER** | Hover in mobile is hard


### CONTENT PARITY
- **All** _functions_ **desktop** in **mobile**
  - **Format** different
  - **Colors** different
  - **Positions** different

## OBSERVATIONS
- In _final_ all is **pixel**
- **em** _font-size:_ **120%** equal _font-size:_ **1.2em**
- **inline-block**
  - The inline-block is interesting by simulating a line of text with its elements. If there is no more _"character"_ on the line, the _"word"_ slides down the line.
- Create **break points** for _YOUR_ **CONTENT**
- **DEBUG**
  - Using **iOS emulator** with _xcode_, _inspect element_ enabled **dev mode** in _safari_
- **weinre** _tool_ for **remote debbug** in **devices**

- **Physical Pixel** | This is __less__ **pixel** in the _display_ _1x1_
- **Device Independent Pixel (DPI or CSS pixel)** | Convert the _css_ pixel in **physical pixel** _2x1_
- **Device Pixel Ratio (dPR)** | Proportion in **Physical Pixel** x **DPI**
  - **dPR** = **Physical Pixel** / **DPIs**
    - **1** _normal_
    - **2** _retina_
- **Few colors** use **PNG 8** _quality_
