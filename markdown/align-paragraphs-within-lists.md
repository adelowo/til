# Aligning (Indenting) paragraphs within list items

```md
-One

Some info about one

-Two

```

This makes it look like `Two` is another list since the comment after `One` isn't aligned. To fix that, you add a blank line and one (or more spaces) before the comment like


-One
 
 Some info about one

-Two


Which gets rendered as 

```md

-One

 Some info about one

-Two
```
