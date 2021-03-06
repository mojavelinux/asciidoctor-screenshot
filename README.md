# AsciiDoctor Screenshot

This Asciidotor package automate your documentation of your webapp using screenshots.
No more hassles when you change simple settings like css or chnage that button that was too big, your documentation stays up to date!

## Quick reference
Basic usage is a bloc *screenshot* that point to an url

```
[screenshot, url=http://google.fr, name=google]
Google Landing page
```

### Parameters
* *url*: the URL to point to. Optional if previously a page was already screenshoot
* *name*: an optional unique id (will be generated otherwise), the screenshot will be called <name>.png
* *dimension*: size of the screenshot for instance 800x600. Try awesomeness with "FRAME_IPHONE4", "FRAME_IPHONE5", "FRAME_SAMSUNG_S4", "FRAME_IMAC" or "FRAME_BROWSER"
* *action="browse"*: all other parameters are ignored, the block following is used to script the browsing. Useful if you need to login beforehand
* *selector*: the css-like dom selector to screenshot. Only this will be part of the image. For instance "div #login_window".

### Examples
```
[screenshot, name=google, url=http://google.com, dimension=FRAME_IMAC]
The Google landing page
```

```
[screenshot, action="browse"]
$("input", name: "q").value("asciidoctor")
waitFor(5){true}
```

```
[screenshot, dimension=FRAME_BROWSER]
Some propositions should appear
```

```
[screenshot, action="browse", dimension=FRAME_IPHONE4]
  $("h3.r a").click()
```

```
[screenshot, dimension=FRAME_SAMSUNG_S4]
Look Ma, it's samsung s4!
```

### DEMO
see Google 101 http://fix.github.io/asciidoctor-screenshot/demo/google.html or Asciidoctor 101 http://fix.github.io/asciidoctor-screenshot/demo
