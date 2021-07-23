# An efficient 40% keyboard layout
I have been fiddling with my 40% layout ever since i got my keyboard, and I believe that I've come up with some good ideas about the 40% layout that I haven't seen anywhere else online. You can upload the keyboard [JSON file](https://github.com/EdvardSire/keyboard/blob/master/niu_mini_layout_planck_mit_mine.json) at [QMK configurator](https://config.qmk.fm/#/) to view the layout layer by layer.

* [TL;DR](https://github.com/EdvardSire/keyboard#the-final-layout)
* [Can you go smaller than 40%?]()
* [Reducing capitalization to on key]()
* [Enter's position on the 4x12]()
* [Numbers without a number row]()
* [Special characters]()
* [The final layout]()
* [The power of QMK](https://github.com/EdvardSire/keyboard#the-power-of-qmk)


## Can you go smaller than 40%?
The reason I bought a 40% was that i wanted the perfect keyboard, by that I mean the smallest possible, yet *efficient*, keyboard. Since i wanted a tiny footprint I went with an ortholinear 1 unit layout, ortholinear doesn't automatically mean smaller, since you can aruge that a keyboard's size is more accurately defined by its number of keys. I personally chose an ortholinear keyboard since i value the grid and smaller footprint. If we messure a keyboard by its grid footprint, I'd argue that a 4x12 keyboard is the perfect keyboard based on the following requirements:

* The letters take up a 3x10 grid
* The ESC and TAB keys on the left
* The Backspace key on the right
* The CTRL, Super and Alt keys naturally spaced in the bottom left
* A centered Spacebar on the bottom row

![Initial keyboard](/images/keyboard-layout-initial.png)


## Reducing capitalization to one key
Coming from something like a >68 key keyboard I think it would be a natural reaction to place Right and Left Shift under TAB and apostrophe ('). I never liked how a >68 key keyboard did capitalization, three keys for one action. I hate capslock, since it's literally just another key held down permanently, but I think it ended up on the >68 layout because of the flawed way the Shift keys are placed. If we assume that one uses the pinky to press Right and Left Shift then this is what the homerow looks like when pressed:

![Shiftkey homerow](/images/keyboard-layout-shiftkey-homerow.png)

Why two Shift keys in the first place? Well I'd aruge that's because when you press Left Shift you can no longer use your left pinky to capitalize Q, A or Z, this goes for Right Shift as well. I think this is an efficiency problem, but also that it's the reason why we traditionally have two Shift key and Capslock, since holding down Right or Left Shift permanently isn't feasible.

One of my problems with the >68 key keyboard is that I never really used my right thumb, and concluding that 3 capitazlization keys comes from the flaw of using them with homerow fingers I found it natural use Shift with my right thumb, like in the image below. This solves capitalizing Q, A and Z with the left pinky and P, (:) and (?) with the right pinky, magically enough this also solves Capslock since the right thumb isn't used for anything else, and can hold down Shift permanently.

![Shift keyboard](/images/keyboard-layout-shift.png)


## Enter's position on the 4x12
I first wanted to move apostrophe (') somewhere else and have Enter under Backspace, but that didn't type well. After mapping Shift one right of Spacebar my right thumb still only had one key to press, so I mapped Enter to the right of Shift. This never becomes a problem since Enter and Shift never has to be pressed at the same time.

![Enter keyboard](/images/keyboard-layout-enter.png)


## Numbers without a number row
The way I mapped Numbers was one of the few things I had a firm idea about when I orignally started tweaking the layout. I knew the Numbers had to be on another layer and decided that i wanted numpad-style Numbers, because I was used to the the numpad with my right hand, the Numbers ended up on the right. I decided to use a [momentary layer switch](https://docs.qmk.fm/#/keycodes?id=layer-switching), which is a feature of QMK. This basically makes the keyboard the second image when the "MO 1" is *pressed down*, when "MO 1" is released the keyboard reverts back to the first image. A momentary layer switch.

![Numbers keyboard](/images/keyboard-layout-numbers-initial.png)

![Numbers-layer keyboard](/images/keyboard-layout-numbers-layer.png)


## Special characters
Since special characters usually mapped to the number row, it was fairly obvious that they had to have their own layer. It would technically be possible to have them on the same layers as the Numbers, but this is unintuitive and unnecesassry. As you can see in the image below most of the Special characters are mapped to their "normal" fingers, but since the keyboard is only 12 units wide I had to make some adjustments. I prioritized (~)-($), deprioritized (%), (^) and (&). I mapped (-) and (=) to my dominant finger(right index) and their correlated (_) and (+) shifted. The parenthesis made extremely sense to me, with ({), and (}) shifted. The backslash is naturally to the left of Backspace and the (|) shifted. (/) can be found on layer 0.

![Special keyboard](/images/keyboard-layout-special-initial.png)

![Speical-layer keyboard](/images/keyboard-layout-special-layer.png)


## The power of QMK
## The final layout
