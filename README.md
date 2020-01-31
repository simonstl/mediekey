# mediekey
# Windows keyboard layout extending Canadian French, for entering old books 

If you're used to English-language keyboards but need to enter texts with lots of foreign characters, Mediekey plus a $20 [HP French-Canadian SK806a keyboard](https://www.newegg.com/p/0GA-0012-006F5?Item=9SIAJCJ8HH2056) or $24 [Dell KB216T C36YV](https://www.newegg.com/p/0GA-002N-005Y7) can help you out. On the fancier side, the [WASD V3 105-Key ISO Custom Mechanical Keyboard](https://www.wasdkeyboards.com/wasd-v3-105-key-iso-custom-mechanical-keyboard.html) is available in Canadian French and fits. (Any 105-key ISO keyboard could work, but the markings will vary.)

If you just need to enter modern documents with more characters than are easily entered with US keyboards, you can just attach the keyboard, [specify to your computer that it's a Canadian French keyboard](https://github.com/simonstl/mediekey/wiki/Installing-the-Canadian-French-layout), and you'll be set to go.  If you need more characters than that supports, however, read on!

The quickest place to see what Mediekey adds is the AltGr display.  These are the characters you get while holding AltGr and another key. (AltGr is also known as the Alt key to the right of the space bar, or Ctrl+Alt.) It also lets you create many more composed characters using this keyboard's wide range of diacritical marks.

![keyboard sample with AltGr](https://raw.githubusercontent.com/wiki/simonstl/mediekey/images/g012020AltGr.png)

The [wiki homepage](https://github.com/simonstl/mediekey/wiki) shows a more complete set, or you can open the [HpSK806a.klc](https://github.com/simonstl/mediekey/blob/master/HpSK806a.klc) file directly in a text editor and read the listings.  That lets you see things like:

```
1e	A		5	a	A	-1	00e6	00c6		// LATIN SMALL LETTER A, LATIN CAPITAL LETTER A, <none>, LATIN SMALL LETTER AE (ash) *, LATIN CAPITAL LETTER AE (ash) *
1f	S		1	s	S	-1	00df	1e9e		// LATIN SMALL LETTER S, LATIN CAPITAL LETTER S, <none>, LATIN SMALL LETTER SHARP S (German), Latin Capital Letter Sharp S
20	D		1	d	D	-1	00f7	-1		// LATIN SMALL LETTER D, LATIN CAPITAL LETTER D, <none>, DIVISION SIGN, <none>
```

or, for keys that combine,

```
DEADKEY	00af

0061	0101	// a -> ā
00e6	01e3	// æ -> ǣ
00c6	01e2	// Æ -> Ǣ
0041	0100	// A -> Ā
0045	0112	// E -> Ē
0065	0113	// e -> ē
0047	1e20	// G -> Ḡ
0067	1e21	// g -> ḡ
0049	012a	// I -> Ī
```


To work with Mediekey, you'll also need the (free but not open source) [Microsoft Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=22339) 1.4 (MKLC).  Mediekey provides a Windows keyboard layout for the Canadian French layout that you can compile and install as part of Français (Canada) language support.  (Unless you have Windows 10 Home Single Language Edition set to a different language, in which case you have to upgrade to Windows 10 Home or Windows 10 Pro first.)

I believe this layout supports all the characters printed on the keyboard, plus a variety of additional characters hiding behind AltGr. Most of them are pharmacy or German letter-combinations used in the old varnish cookbooks I've been typing in. For this first round, I'm using dead keys to create composed characters, including many that are unusual in current Latin alphabet use, but I may also do another version that uses Unicode combining characters.  (That will provide vastly more flexibility and be easier to maintain, but will create issues with some kinds of software.)

The key file you need from this project is [HpSK806a.klc](https://github.com/simonstl/mediekey/blob/master/HpSK806a.klc).  This contains the information MKLC needs to let you edit the layout or compile an installer that will let you use the layout. [Installation instructions cover the many steps needed](https://github.com/simonstl/mediekey/wiki/Installing-the-Mediekey-layout).

This project is licensed under the [Hippocratic License](https://firstdonoharm.dev/). Please [use it for good](http://simonstl.com/random/2013/06/code_like_youre_writing.html).

# Why

I wanted to enter a variety of medieval and early modern European documents, but found myself too constrained by the options easily available on US Standard keyboards.  At the same time, I wanted to stick with the QWERTY layout, because past experience had taught me that I don't change quickly or easily. (Most of my work is still done on US Standard.) I installed the Français (Canada) language pack, but on-screen keyboards aren't much fun for extended typing or more than very occasional characters.

I went looking for a QWERTY keyboard that supported a lot of additional characters, and found the [HP French-Canadian SK806a keyboard](https://www.newegg.com/p/0GA-0012-006F5?Item=9SIAJCJ8HH2056).  It arrived, and I started typing, and it didn't work, and I figured there must be a magic switch to fix it, and... nothing. It turns out that [Canadian French](https://en.wikipedia.org/wiki/File:KB_Canadian_French_text.svg) works, but wasn't near the top of the list for reasons I still don't understand. (I should have looked for Canadian, not French. Hmmm....)

My failure worked out great, though. Eventually I found the [Microsoft Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=22339) 1.4 (MKLC), an old and dusty piece of software that wants a specific version of .NET to run.  It was reasonably self-explanatory, though, and I cobbled together a first workable version of a layout. The layout files are reasonably simple, but every time I want to make a change, I get to remove the old layout in settings, run the old installer to remove it, create a new installer from MKLC, and install that. 

It's clunky, but it's still an improvement.  The results are much more flexible than just installing the Canadian French layout, letting me set dead keys and extend the capabilities of the keyboard. (In my perfect world, using Unicode combining characters would be easy and well-supported, but I don't see that happening soon.)

Need to find a character?  This [chart of Unicode characters organized by shape](http://www.unicode.org/charts/collation/) can be extremely useful.

# Note on the .KLC format

GitHub treats the .KLC file as binary, I think because it's a UTF-16LE file.  That means it's text, but expressed somewhat more verbosely than the usual UTF-8. If you edit the file in GitHub, it will save it as UTF-8. In my experiments MKLC will still open a file saved as UTF-8, but will save it back out as UTF-16LE.  This probably only matters if you want to edit the file directly with an old text editor, but even a recent version of Notepad was able to open and explore it.
