# sfos-baseicon
Base SVG to help preparing icons for Sailfish OS.

It uses SVG clipping, which not all programs support, Inkscape seems to work fine
 – use its XML Editor to change classes or to drag elements into the clipped area.

### Clipping
The base icon contains a clip path to create all standard icon shapes for SFOS
using CSS classes on the svg base element.
without any classes, the shape is a circle, but you can add corners by adding the classes `tl`,
`tr`, `bl` and/or `br` to the svg element. Put extra svg elements into the g element
(id="clippedContent") for them to be cut into that shape. You should probably change the
black Background Rectangle as well.

By default, the class is "`tl tr`" and clips content like this:

![class tl tr](https://i.imgur.com/9eYZatt.png)

### Sizes
On a linux bash with Inkscape you could do something like the following to export
the png file to different sizes:


    for dimension in 86 108 128 256; \
    do \
    mkdir -p "${dimension}x${dimension}"; \
    inkscape -f sfos-baseicon.svg -w $dimension -h $dimension -e "${dimension}x${dimension}/icon.png"; \
    done
