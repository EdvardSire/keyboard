# An efficient 40% keyboard layout

Todo

- Proofread
- Reformulate lower portion
- Add numlock
- Remake some of the images to be consistent with new keys added

This is the summary of my 40% keyboard layout. This essay reflects my process of designing an “optimal” keyboard layout. You can view the layout layer by layer at [QMK configurator](https://config.qmk.fm/#/) by uploading one of the [JSON files](https://github.com/EdvardSire/keyboard/blob/master/niu_mini_layout_planck_mit_mine_clean.json). If the resonating process doesn’t interest you, feel free to skip to [The final layout](https://github.com/EdvardSire/keyboard#the-final-layout) section.

- [Why 40%](https://github.com/EdvardSire/keyboard#why-40%?)
- [Motivation](https://github.com/EdvardSire/keyboard#motivation)
- [Reducing capitalization to one key](https://github.com/EdvardSire/keyboard#reducing-capitalization-to-one-key)
- [The power of QMK](https://github.com/EdvardSire/keyboard#the-power-of-qmk)
- [Numbers without a number row](https://github.com/EdvardSire/keyboard#numbers-without-a-number-row)
- [Special characters](https://github.com/EdvardSire/keyboard#special-characters)
- [Making the keyboard complete](https://github.com/EdvardSire/keyboard#making-the-keyboard-complete)
- [The final layout](https://github.com/EdvardSire/keyboard#the-final-layout)

## Why 40%?

When I was searching for a new keyboard back in 2019 I realised that I was looking for the smallest possible, yet _efficient_, keyboard. I decided that I wanted an ortholinear keyboard since it minimizes the keyboard footprint. But you can argue that absolute keyboard size is more accurately defined by the number of keys. Anyways, I concluded that a 40%, more specifically a 4x12, is the smallest keyboard that meets the following requirements:

- QWERTY on a 3x10 grid
- ESC and TAB on the left
- Backspace on the right
- The CTRL, Super, Alt and Spacebar on the bottom

![Initial keyboard](/images/keyboard-layout-initial.png)

## Motivation

The purpose of the layout is to combine a small footprint with an efficient layout. A 4x12 footprint results in the fact that the fingers can stay on the home row. This is intrinsically efficient but has to be combined with a sensible layout that doesn’t restrict typing speed or usability.

## Reducing capitalization to one key

I think anyone coming from a keyboard with 68 keys or more would naturally place Right and Left Shift under TAB and apostrophe ('), and Capslock somewhere on the bottom row. I think that having three keys for capitalization is ludicrous from an efficiency standpoint. In addition to the fact that when your “home row pinkies” press Shift, like in the image below, you can no longer press Q, A, Z, or P with their dedicated fingers. One could argue that this quirk of Shift placement doesn’t necessarily affect typing speed, but I fundamentally dislike it and believe that capitalization should be done differently.

![Shiftkey homerow](/images/keyboard-layout-shiftkey-homerow.png)

Why two Shift keys in the first place? I’d argue that it stems from the capitalization problem of A, Q, Z, and P. This is (I guess) also the reason why we have Caps Lock, since holding down Right or Left Shift permanently isn't feasible.

Okay, how do we improve this? The reason for multiple Shift keys is that the home row pinkies can’t be held down permanently, this is what creates the need for Caps Lock. That means that if we solve Shift keys we don’t need Caps Lock. And the problem with Shift keys is that their fingers, the pinkies, are needed for other important keys. In fact, it doesn’t make sense to use **any** of the home row fingers for capitalization, because they press the letters to capitalize. That’s why using the non-Spacebar-thumb for Shift magically reduces capitalization to one key, since it can be held down permanently.

![Shift keyboard](/images/keyboard-layout-shift.png)

## The power of QMK

At this point it might seem like the layout is running out of keys, yes, but actually no. [QMK](https://qmk.fm) (Quantum Mechanical Keyboard) is an amazingly powerful keyboard firmware tool that most custom keyboards support. It makes the layers in my layout possible, but it has more complex features built in and makes it possible to program your own. I'd recommend checking out all the built in features at [QMK config](https://config.qmk.fm).

## Numbers without a number row

The way I mapped Numbers was one of the few things I had a firm idea about when I orignally started tweaking the layout. I knew the Numbers had to be on another layer and decided that i wanted numpad-style Numbers, because I was used to using the numpad with my right hand. I decided to use a QMK [momentary layer switch](https://docs.qmk.fm/#/keycodes?id=layer-switching). This basically switches the keyboard layout to the second image when the "MO 1" is _pressed down_. When "MO 1" is released the keyboard reverts back to the first image. This is convenient and fast since the fingers doesn't have to move.

![Numbers keyboard](/images/keyboard-layout-numbers-initial.png)

![Numbers-layer keyboard](/images/keyboard-layout-numbers-layer.png)

## Special characters

Since special characters are usually mapped to the number row, it was fairly obvious that they had to have their own layer. It would technically be possible to have them on the same layers as the Numbers, but this is unintuitive and unnecesassry. As you can see in the image below most of the Special characters are mapped to their "normal" fingers, but since the keyboard is only 12 units wide I had to make some adjustments. I prioritized (~)-($), deprioritized (%), (^) and (&). I mapped (-) and (=) to my dominant finger(right index) and their correlated (\_) and (+) shifted. The parenthesis' are comfortable to press with the two in-the-middle homerow-fingers, ({) and (}) are shifted. The backslash is naturally to the left of Backspace and the (|) shifted. (/) and other important Special characters can be found on layer 0.

![Special keyboard](/images/keyboard-layout-special-initial.png)

![Special-layer keyboard](/images/keyboard-layout-special-layer.png)

## Arrow keys and Function keys

Other small keyboard usually have the arrow keys in the bottom right corner, but I think it's much more efficient and comfortable to have them on the home row. Since the Arrow keys only require 3 fingers, using the pinkie finger is natural. The key under apostrophe (') was natural and convenient. I later realized that I needed Function keys (surprise, surprise), but they were easy to just dump on the left side of the Arrow keys.

![Arrows keyboard](/images/keyboard-layout-arrows-initial.png)

![Arrows-layer keyboard](/images/keyboard-layout-arrows-layer.png)

## Making the keyboard complete

To finish up the layout i use some more QMK features which result in the following:

- The "escape key" is normally ESC, but now (~) when shift is pressed
- The Shift and Enter keys from before are combined into one: Enter when pressed, Shift when held down
- The Del key is now on the bottom right
- Layer 1 is updated
- Layer 4 is new

![QMK keyboard](/images/keyboard-layout-qmk.png)

In addition to numbers this layer now has Media keys, a Power key, a Reset key and RGB control.

![QMK-numbers keyboard](/images/keyboard-layout-numbers-qmk.png)

This new layers makes it possible to control the cursor without a mouse, not practical, but possible.

![QMK-mouse keyboard](/images/keyboard-layout-mouse.png)

## The final layout

{::comment}

## Enter's position on the 4x12

Continue from here

I first wanted to move apostrophe (') somewhere else and have Enter under Backspace, but that didn't type well. After mapping Shift one right of Spacebar my right thumb still only had one key to press, so I mapped Enter to the right of Shift. This never becomes a problem since Enter and Shift never has to be pressed at the same time. When QMK is introduced enter's position is improved.

![Enter keyboard](/images/keyboard-layout-enter.png)
{:/comment}
