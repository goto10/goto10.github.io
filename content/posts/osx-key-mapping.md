---
title: "OSX Key Mapping"
description: "Fix those pesky home and end keys."
featured_image: '/images/posts/homeKey.jpg'
date: 2020-05-14T14:57:21-07:00
---

Change default key mapping

After years of being annoyed every time I would hit the end key on my keyboard, wanting to get to the end of the line I was current  on but instead I would end up at the bottom of the file I was in. I have finally found the solution to this problem. 

All we need to do is edit the key bindings file, or in most cases create the file. 
~/Library/DefaultKeyBinding.dict

First we will create the file. Don't worry if the file already exists this is still safe to run.  
From the terminal run:
``` bash linedivs
touch ~/Library/DefaultKeyBinding.dict
```

Then edit the file by running:  
(This will open the file in your default text editor.)
``` bash linedivs
open  ~/Library/DefaultKeyBinding.dict
```

Paste these setting into the file.
```
{
  "\UF729"  = moveToBeginningOfParagraph:;                   // home
  "\UF72B"  = moveToEndOfParagraph:;                         // end
  "$\UF729" = moveToBeginningOfParagraphAndModifySelection:; // shift-home
  "$\UF72B" = moveToEndOfParagraphAndModifySelection:;       // shift-end
  "@\UF729" = moveToBeginningOfDocument:;                    // cmd-home
  "@\UF72B" = moveToEndOfDocument:;                          // cmd-end
  "@$\UF729" = moveToBeginningOfDocumentAndModifySelection:; // cmd-shift-home
  "@$\UF72B" = moveToEndOfDocumentAndModifySelection:;       // cmd-shift-end
}
```

If you want to modify the key combinations, here are the special key modifiers, just put them in front of the \  
^ == Ctl  
@ == Command  
$ == Shift  
~ == Option (Alt)

Once you're done save the file and Reboot for the changes to take effect.
