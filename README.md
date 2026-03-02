# ThWERTEe Shaw Layout

ThWERTEe is a QWERTY-derived keyboard layout for the Shavian alphabet. <br/>
It's available for XKB (Linux) and Heliboard (Android).

## Table of Contents

- [Features](#features)
- [Installation](#installation)
   * [Supported Keyboards](#supported-keyboards)
   * [Installing on XKB](#installing-on-xkb)
   * [Installing on Heliboard](#installing-on-heliboard)
- [Additional Usage Notes](#additional-usage-notes)
   * [Extended Shavian](#extended-shavian)
 

## FEATURES

The intent of this Shavian layout is to preserve as much of the muscle-memory for QWERTY, english-speaking, latinic typing as possible. Many of the keys retain the most-frequent phoneme of the latinic character, but in the Shavian script (especially consonants). 
> 👉 **EXAMPLE:** <br/>
> W, R, T, P, S, D, F, H, L, Z, V, B, N, and M are all on the same, unshifted keys. 

I designed this layout to feel intuitive and accessible for newcomers to Shavian who are already used to standard QWERTY. I've also been dissatisfied with the astounding number of Shavian layouts that map Shavian characters to non-letter keys, rendering intuitive typing effectively impossible in my experience. 

This layout supports the extended Shavian characters by the inclusion of the Variation Selector 1 key. It will be referred to as `VS1` in this repo, and is located on shifted `N`. <br/>
See [Extended Shavian](#extended-shavian) for a list of supported typefaces. 


#### Layout Screenshots

![ThWERTEe Desktop Layout Map](images/ThWERTEe_desktop.png)

![ThWERTEe Mobile Layout Map](images/ThWERTEe_mobile.png)

## INSTALLATION

### Supported Keyboards

ThWERTEe is currently available for use on the Heliboard keyboard app on Android, and on XKB on Linux. 

### Installing on XKB 

> [!IMPORTANT]
> You will need root/admin permissions on your Linux machine to modify the configuration files. This is largely because XKB doesn't have a simple or intuitive way to install custom layouts to my knowledge. 

> [!CAUTION]
> These instructions have worked for me, but I can't guarantee they will work for you, and in the worst case they could make your keyboard unusable. Proceed with caution.

1. **Locate where XKB stores its config files on your machine:** <br/>
For my Fedora 42 machine, it's `/usr/share/X11/xkb/`, but the file structure differs between certain distributions so you _will_ have to do some legwork on your own here. <br/>
This directory will be referred to as `[xkb]` for the installation steps.

2. **Put the layout file in the layout folder:** <br/>
Copy the file `shavian` to `[xkb]/symbols/`. 

3. **Make a backup of your original `evdev.xml` file:** <br/>
Copy `[xkb]/rules/evdev.xml` to another folder as a backup (e.g.; Desktop, Documents, etc.). This step is crucial, because if you perform these steps incorrectly then your keyboard can easily become unusable, and making it usable again will be _much_ more difficult without a backup.

4. **Insert the addendum code into `evdev.xml`:** <br/>
Open `[xkb]/rules/evdev.xml`, find the line that says `</layoutList>` (make sure the slash is there), and insert the contents of `add_to_evdev.xml` directly before that line. 

4. **Restart your computer:** <br/>
Reboot so the changes are put into effect. This step might not be necessary depending on your machine and distribution.

5. Open your System Settings and go to Keyboard > <ins>🞢 Add...</ins>. Type in "`Shavian`" in the search, select your new layout, and click <ins>OK</ins>. 

You should now be able to type in Shavian in the ThWERTEe layout on your Linux!

> [!IMPORTANT]
> Sometimes an update will overwrite `[xkb]/rules/evdev.xml`, so if the layouts stop working at some point, you may need to repeat steps 3 and 4.

If you've followed these instructions correctly and they still don't work, [contact me](https://iykury.xyz/contact/) so I can update them.

### Installing on Heliboard

Installing on [Heliboard](https://github.com/Helium314/HeliBoard) is straightforward, and creating/editing layouts is relatively [well-documented](https://github.com/Helium314/HeliBoard/wiki/2.-Layouts):

1. **Open the Heliboard settings:** <br/>
Either tap Heliboard in your apps or long-pressing the comma key and slide it to the gear icon (or whichever key you may have remapped it to). 

2. **Add a new language profile:** <br/>
Tap <ins>Languages & Layouts</ins> at the top, and then either <ins>English</ins> in your locality or <ins>No language</ins> (I've found standard English to work better with adding words to the internal dictionary). 

3. **Create a new keyboard layout file:** <br/>
At the top, under <ins>Layout</ins>, tap the **🞢** icon. An ephemeral will pop up about adding custom layouts; just tap <ins>OK</ins>. 

4. **Copy the code:** <br/>
Switch over to your browser (or however you're accessing this repo), open [ThWERTEe_mobile](heliboard/ThWERTEe_mobile.JSON), and copy the code to your clipboard. (Technically this step can be done at any point before the next step.)

5. **Paste the code into the layout file:** <br/>
Name the file at the top; "ThWERTEe" makes the most sense, but you do you. Paste the code in the next text field and press <ins>Save</ins>. 

> [!NOTE]
> If the <ins>Save</ins> button is greyed out and you can't tap it, it means that the code is out of format; either go back and re-copy it from the repo or  undo any edits you may have done. 
> If you were customizing the layout on your own, you can also check your formatting for errors [here](https://jsoneditoronline.org/) and/or check [the docs](https://github.com/Helium314/HeliBoard/wiki/2.-Layouts).

6. **Customize the rest of your settings:** <br/>
Make sure the pop up source and order settings work for you; this may require playing with the keyboard and testing things.

7. **Use your new layout:** <br/>
Switch to your new layout by holding down `,` and swiping to the `🌐` icon (the shortcut by default). If you'd prefer a designated key to switch language, go to <ins>Preferences</ins> > <ins>Additional keys</ins> > <ins>Language switch key</ins>. 

You should now be able to type in Shavian in the ThWERTEe layout on Heliboard!

## Additional Usage Notes

### Extended Shavian

> [!TIP]
> The use of `VS1` allows you to type some extra Shavian characters not included in Unicode. These characters are extraneous for most applications, but may be useful in cases where conveying very specific pronunciation is necessary - such as in proper nouns or pronunciation notation. <br/>
> If a typeface or the fallback font doesn't support extended Shavian characters, `VS1` will simply have no effect on the displayed character.

#### Full Support Typefaces
- [Inter Alia](https://github.com/Shavian-info/interalia) 
- [Playwrite Shavian](https://2gd4.me/tidbit/shavian-fonts.html#playwrite) - based on Playwrite by TypeTogether
- [Couth #48 & #43](https://2gd4.me/tidbit/shavian-fonts.html#couth) - based on Courier Prime
- [Hypercam](https://2gd4.me/tidbit/shavian-fonts.html#hypercam) - based on MS Windows 2 system font
- [Atlanta](https://2gd4.me/tidbit/shavian-fonts.html#atlanta) - based on Georgia

#### Limited Support Typefaces
- [Hal](https://2gd4.me/tidbit/shavian-fonts.html#hal) - based on CGA 8×16 system font; available in sans and serif
- [Iotacism #43](https://2gd4.me/tidbit/shavian-fonts.html#iotacism) - based on Iosevka by Belleve Invis
- [Allstars](https://2gd4.me/tidbit/shavian-fonts.html#allstars) - based on the text from Super Mario All-Stars









