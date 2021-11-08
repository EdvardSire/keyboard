# An efficient 40% keyboard layout

TODO
- add backtick

I have been tweaking my 40% keyboard layout since 2019, and I believe that I've come up with some good ideas that I haven't seen anywhere else online. Most of the paragraphs are about how I reasonated to the implementation, but the last heading is more descriptive. You can view the layout layer by layer by uploading the [QMK JSON file](https://github.com/EdvardSire/keyboard/blob/master/niu_mini_layout_planck_mit_mine_clean.json) at [QMK configurator](https://config.qmk.fm/#/) for better visuals.

* [TL;DR](https://github.com/EdvardSire/keyboard#the-final-layout)
* [Can you go smaller than 40%?](https://github.com/EdvardSire/keyboard#can-you-go-smaller-than-40)
* [Reducing capitalization to one key](https://github.com/EdvardSire/keyboard#reducing-capitalization-to-one-key)
* [Enter's position on the 4x12](https://github.com/EdvardSire/keyboard#enters-position-on-the-4x12)
* [Numbers without a number row](https://github.com/EdvardSire/keyboard#numbers-without-a-number-row)
* [Special characters](https://github.com/EdvardSire/keyboard#special-characters)
* [The power of QMK](https://github.com/EdvardSire/keyboard#the-power-of-qmk)
* [The final layout](https://github.com/EdvardSire/keyboard#the-final-layout)


## Can you go smaller than 40%?
The reason I bought a 40% was that i wanted the perfect keyboard, by that I mean the smallest possible, yet *efficient*, keyboard. Since i wanted a tiny footprint I went with an ortholinear 1 unit layout, ortholinear doesn't automatically mean smaller, since you can aruge that a keyboard's size is more accurately defined by its number of keys. I personally chose an ortholinear keyboard since i value the grid and smaller footprint. If we messure a keyboard by its grid footprint, I'd argue that a 4x12 keyboard is the perfect keyboard based on the following requirements:

* The letters take up a 3x10 grid
* The ESC and TAB keys on the left
* The Backspace key on the right
* The CTRL, Super and Alt keys naturally spaced in the bottom left
* A centered Spacebar on the bottom row

![Initial keyboard](/images/keyboard-layout-initial.png)


## Reducing capitalization to one key
Coming from something like a >68 key keyboard I think it would be a natural reaction to place Right and Left Shift under TAB and apostrophe ('). I never liked how a >68 key keyboard did capitalization, three keys for one action. I hate capslock, since it's literally just another key held down permanently, but I think it ended up on the >68 layout because of the flawed way the Shift keys are placed. If we assume that one uses the pinky to press Right and Left Shift then this is what the home row looks like when pressed:

![Shiftkey homerow](/images/keyboard-layout-shiftkey-homerow.png)

Why two Shift keys in the first place? Well I'd aruge that's because when you press Left Shift you can no longer use your left pinky to capitalize Q, A or Z, this goes for Right Shift as well. I think this is an efficiency problem, but also that it's the reason why we traditionally have two Shift key and Capslock, since holding down Right or Left Shift permanently isn't feasible.

One of my problems with the >68 key keyboard is that I never really used my right thumb, and concluding that 3 capitazlization keys comes from the flaw of using them with home row fingers I found it natural use Shift with my right thumb, like in the image below. This solves capitalizing Q, A and Z with the left pinky and P, (:) and (?) with the right pinky, magically enough this also solves Capslock since the right thumb isn't used for anything else, and can hold down Shift permanently.

![Shift keyboard](/images/keyboard-layout-shift.png)


## Enter's position on the 4x12
I first wanted to move apostrophe (') somewhere else and have Enter under Backspace, but that didn't type well. After mapping Shift one right of Spacebar my right thumb still only had one key to press, so I mapped Enter to the right of Shift. This never becomes a problem since Enter and Shift never has to be pressed at the same time.

![Enter keyboard](/images/keyboard-layout-enter.png)


## Numbers without a number row
The way I mapped Numbers was one of the few things I had a firm idea about when I orignally started tweaking the layout. I knew the Numbers had to be on another layer and decided that i wanted numpad-style Numbers, because I was used to using the numpad with my right hand, the Numbers ended up on the right. I decided to use a [momentary layer switch](https://docs.qmk.fm/#/keycodes?id=layer-switching), which is a feature of QMK. This basically makes the keyboard the second image when the "MO 1" is *pressed down*, when "MO 1" is released the keyboard reverts back to the first image. A momentary layer switch.

![Numbers keyboard](/images/keyboard-layout-numbers-initial.png)

![Numbers-layer keyboard](/images/keyboard-layout-numbers-layer.png)


## Special characters
Since special characters are usually mapped to the number row, it was fairly obvious that they had to have their own layer. It would technically be possible to have them on the same layers as the Numbers, but this is unintuitive and unnecesassry. As you can see in the image below most of the Special characters are mapped to their "normal" fingers, but since the keyboard is only 12 units wide I had to make some adjustments. I prioritized (~)-($), deprioritized (%), (^) and (&). I mapped (-) and (=) to my dominant finger(right index) and their correlated (_) and (+) shifted. The parenthesis' made extremely sense to me, with ({), and (}) shifted. The backslash is naturally to the left of Backspace and the (|) shifted. (/) and other important Special characters can be found on layer 0.

![Special keyboard](/images/keyboard-layout-special-initial.png)

![Special-layer keyboard](/images/keyboard-layout-special-layer.png)


## Arrow keys and Function keys
Other small keyboard usually have the arrow keys in the bottom right corner, but I think it's much more efficient and comfortable to have them on the home row. Since the Arrow keys only require 3 fingers, the key under apostrophe (') was natural and convenient to use as the Arrow key layer. I later realized that I needed Function keys (surprise, surprise), but they were easy to just dump on the left side of the Arrow keys.

![Arrows keyboard](/images/keyboard-layout-arrows-initial.png)

![Arrows-layer keyboard](/images/keyboard-layout-arrows-layer.png)


## The power of QMK
[QMK](https://qmk.fm) (Quantum Mechanical Keyboard) is an amazingly powerful keyboard firmware tool that most custom keyboards support. It makes the layers in my layout possible, but it has more complex features built in and makes it possible to program your own. I'd recommend checking out all the built in features at [QMK config](https://config.qmk.fm), here are the ones I find useful:

![QMK keyboard](/images/keyboard-layout-qmk.png)

* The "escape key" is normally ESC, but now (~) when shift is pressed
* The Shift and Enter keys from before are combined into one: Enter when pressed, Shift when held down
* The Del key is now on the bottom right
* Layer 1 is updated
* Layer 4 is new

![QMK-numbers keyboard](/images/keyboard-layout-numbers-qmk.png)

In addition to numbers this layer now has Media keys, a Power key, a Reset key and RGB control.

![QMK-mouse keyboard](/images/keyboard-layout-mouse.png)

This new layers makes it possible to control the cursor without a mouse, not practical, but possible.

## The final layout
