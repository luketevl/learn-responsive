# learn-responsive
Learning responsive

## LINKS

- http://www.w3.org/TR/css3-mediaqueries/
- http://www.dropboxwiki.com/tips-and-tricks/host-websites-with-dropbox
- https://developer.chrome.com/devtools/docs/remote-debugging
- https://www.npmjs.com/package/weinre

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
  - **To text** use **em**

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
- **MAX-WIDTH** | _Does not allow_ the image to **exceed its maximum size**
```css
img{
  max-width: 100%;
}
```

#### MEDIA QUERIES
- _Do think_ **MOBILE FIRST** | Write css default in **mobile** and add _break points_ in _media queries_ **desktop**
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

#### VIEWPORT
- **Added** **viewport** to _alert mobile_ that your page is _responsive_
```html
<!-- AUTOMATIC MODE RECOMMEND-->
<meta name='viewport' content='width=device-width'>

<!-- MANUAL MODE -->
<meta name='viewport' content='width=320'>
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

## OBSERVATIONS
- In _final_ all is **pixel**
- **em** _font-size: **120%** equal _font-size:_ **1.2em**
- **inline-block**
  - The inline-block is interesting by simulating a line of text with its elements. If there is no more _"character"_ on the line, the _"word"_ slides down the line.
- Create **break points** for _YOUR_ **CONTENT**
- **DEBUG**
  - Using **iOS emulator** with _xcode_, _inspect element_ enabled **dev mode** in _safari_
- **Viewport** to **iOS** use:
```html
<meta name="viewport" content="width=device-width, initial-scale=1">.
```
- **weinre** _tool_ for **remote debbug** in **devices**
