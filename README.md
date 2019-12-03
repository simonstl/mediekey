# mediekey
# Windows keyboard layout extending Canadian French, for entering old books 

If you're used to English-language keyboards but need to enter texts with lots of foreign characters, Mediekey plus a $20 [HP French-Canadian SK806a keyboard](https://www.newegg.com/p/0GA-0012-006F5?Item=9SIAJCJ8HH2056) or $24 [Dell KB216T C36YV](https://www.newegg.com/p/0GA-002N-005Y7). You'll also need the (free but not open source) [Microsoft Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=22339) 1.4 (MKLC).  Mediekey provides a Windows keyboard layout for the Canadian French layout that you can compile and install as part of Français (Canada) language support.

I believe this layout supports all the characters printed on the keyboard, plus a variety of additional characters hiding behind AltGr. Most of them are pharmacy or German letter-combinations used in the old varnish cookbooks I've been typing in. (Oops.  I still have to add support for the macron and macron below.)

The key file you need from this project is [HpSK806a.klc](https://github.com/simonstl/mediekey/blob/master/HpSK806a.klc).  This contains the information MKLC needs to let you edit the layout or compile an installer that will let you use the layout.  

This project is licensed under the [Hippocratic License](https://firstdonoharm.dev/). Please [use it for good](http://simonstl.com/random/2013/06/code_like_youre_writing.html).

# Why

I wanted to enter a variety of medieval and early modern European documents, but found myself too constrained by the options easily available on US Standard keyboards.  At the same time, I wanted to stick with the QWERTY layout, because past experience had taught me that I don't change quickly or easily. (Most of my work is still done on US Standard.) I installed the Français (Canada) language pack, but on-screen keyboards aren't much fun for extended typing or more than very occasional characters.

I went looking for a QWERTY keyboard that supported a lot of additional characters, and found the [HP French-Canadian SK806a keyboard](https://www.newegg.com/p/0GA-0012-006F5?Item=9SIAJCJ8HH2056).  It arrived, and I started typing, and it didn't work, and I figured there must be a magic switch to fix it, and... nothing. It turns out that [Canadian French](https://en.wikipedia.org/wiki/File:KB_Canadian_French_text.svg) works, but wasn't near the top of the list for reasons I still don't understand. (I should have looked for Canadian, not French. Hmmm....)

My failure worked out great, though. Eventually I found the [Microsoft Keyboard Layout Creator](https://www.microsoft.com/en-us/download/details.aspx?id=22339) 1.4 (MKLC), an old and dusty piece of software that wants a specific version of .NET to run.  It was reasonably self-explanatory, though, and I cobbled together a first workable version of a layout. The layout files are reasonably simple, but every time I want to make a change, I get to remove the old layout in settings, run the old installer to remove it, create a new installer from MKLC, and install that. 

It's clunky, but it's still an improvement.  The results are much more flexible than just installing the Candian French layout, letting me set dead keys and extend the capabilities of the keyboard.

# Note on the .KLC format

GitHub treats the .KLC file as binary, I think because it's a UTF-16LE file.  That means it's text, but expressed somewhat more verbosely than the usual UTF-8. If you edit the file in GitHub, it will save it as UTF-8. In my experiments MKLC will still open a file saved as UTF-8, but will save it back out as UTF-16LE.  This probably only matters if you want to edit the file directly with an old text editor, but even a recent version of Notepad was able to open and explore it.