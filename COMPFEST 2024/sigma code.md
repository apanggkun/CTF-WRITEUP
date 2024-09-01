# CTF Writeup: [CTF Event Name]

## Challenge Name

- Category: Misc
- Points: 100
- Description: My mewing robot is trying to tell me something
- Author: Keego

## Solution

It's an audio file that spits out numbers. My first thought is that it's ASCII, and when I write down the numbers, it becomes the flag.
```
81 48 57 78 85 69 90 70 85 49 81 120 78 110 116 53 78 72 108 102 77 122 86 107 77 68 89 49 77 84 78 107 90 72 48 61 
```

Using [Ascii to Text][asciiToTextConverter], I confirmed that it is ASCII and the result is `Q09NUEZFU1QxNnt5NHlfMzVkMDY1MTNkZH0=`. By the looks of it, it appears to be base64 encoding. So, I tried decoding it with [CyberChef][CyberChef] and obtained the flag.


## Flag

The Flag : COMPFEST16{y4y_35d06513dd}



[CyberChef]: https://gchq.github.io/CyberChef/
[asciiToTextConverter]: https://www.duplichecker.com/ascii-to-text.php