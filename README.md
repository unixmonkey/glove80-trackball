# Glove80-Trackball

Trackball sidecar mod for the Glove80 keyboard with the internals of a Logitech ERGO M575

![glove80-trackball](https://github.com/user-attachments/assets/fc9dc3ec-b8bb-4951-b5b0-7521a6ddd192)

## Why

I recently started getting RSI-like pain and went on a deep dive into the word of ergonomic split keyboards, but I knew a large part of my issue was my mouse usage habits, and that moving from the keyboard to the mouse (or trackpad) over and over again certainly wasn't helping.

Unfortunately, there currently are very few commercially available ergonomic keyboards that have built-in pointing devices.
However, the [MoErgo Glove80](https://www.moergo.com/collections/glove80-keyboards) keyboard tries to be highly ergonomic, as well as [customizable](https://www.moergo.com/pages/glove80-ergonomic-keyboard-customization) platform, and even provides built-in anchor points and some basic 3d models that can be used to add your own pointing devices right between the thumb cluster and forefinger areas. I figured this could be how I could possibly _make_ the Glove80 the perfect keyboard for me.

So I bought the Glove80, and a 3d printer, and got to work. This is helping me, and so I hope my efforts can help others.

## What you'll need

1. The [MoErgo Glove80 keyboard](https://www.moergo.com/collections/glove80-keyboards)
2. A 3D printer (or a friend/library/makerspace/business with one)
3. [Logitech Ergo M575 Wireless Trackball mouse]([https://ergonomictouchpad.com/ergonomic_touchpad.php](https://www.logitech.com/en-us/products/mice/m575-ergo-wireless-trackball.910-005868.html))
4. 2.5mm screws (for the Glove80 mounting holes). I'm using 8mm deep ones I got in [this kit](https://www.amazon.com/dp/B0BLCFD9HR)
5. These [3d model files](/models/)

## Assembly

The internals are meant to be laid out like this:

<img width="350" src="https://github.com/user-attachments/assets/a0eda7b7-9e3c-4f9b-ac82-552a1bf7dc54">

However, the tolerances aren't great right now, and I ended up just hot-gluing the parts to the top shell.

Also included in the models dir, is this earlier (v6) model:

<img width="350" src="https://github.com/user-attachments/assets/901ff422-82c7-4af7-930e-33f292bd5adc">

<img width="350" src="https://github.com/user-attachments/assets/b254c3e7-88ef-43cb-8a7b-13cf7ffdab13">

This one has a more accurate ball hole, but needed a little cutting around the inner mount and above the "6" key to fit properly.

If you can help make this better, please create a Pull request or issue to discuss.

If you find that the included ribbon cables are too short, first swap them and use the longer one. Otherwise, [these](https://www.amazon.com/dp/B07RWTFSG7) replacement ones work, and are much longer.

## Glove80 mouse-keys configuration

Because the trackball we've just printed doesn't have the mouse buttons wired up, we probably want to map some keys on the Glove80 to act as mouse buttons.
I've setup the 2 right and bottom-most thumb keys to act as mouse buttons in [my layout](https://my.glove80.com/#/layout/user/2e9038ef-1ab4-45dc-9edd-4a34c662d1fc) by assigning them to the "CUSTOM" behavior with `&mkp MB1` for left-click and `&mkp MB2` for right-click (I did not setup middle-click).

![thumb-buttons](https://github.com/user-attachments/assets/51838a18-f06e-4d03-8430-dec2b59a7873)

It is not at all necessary, but you might consider setting up a "mouse" layer like mine above, now that you will be building a firmware capable of emulating a mouse, you might want to take advantage of that.

By default, the MoErgo editor does not build a ZMK firmware with mouse support, so after saving your changes, but before building the firmware, go to "settings" at the top, and change the firmware to "community.pr23.mouse-keys.20240223.113355" or the modern equivalent you see there. One day, ZMK should merge mouse support into main, and this step may not be needed any longer.
![mouse-pr](https://github.com/user-attachments/assets/9fc0f0fd-7894-47cb-8bb1-e3797d4ec1f4)

Once you flash your Glove80 with the new firmware, these keys should act as mouse buttons.

## TODO

- Fix the bottom plate so all the parts fit as expected, and the power switch is accessible
- I'm currently working on a version that also uses the Ergo M575 scroll-wheel & buttons (either by using the existing mouse switches, or soldering in some Kailh ones.

## See Also

- My [Glove80 Ergo Trackpoint mod](https://github.com/unixmonkey/glove80-trackpoint)
- My [Glove80 Touchpad](https://github.com/unixmonkey/glove80-touchpad)
