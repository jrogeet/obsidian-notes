---
Course: CS50
Topic: Binary
Week: 1
tags:
  - computerscience
  - cs50
  - c_lang
---
## Binary
![[Pasted image 20240626182049.png]]


## ASCII
- Letters are represented by 0's and 1's too
- If you received a text message, the binary under that message might represent the numbers 72, 73, and 33. Mapping these out to ASCII, your message would look as follows:
    
    ```
    H   I   !
    72  73  33
    ```

![[Pasted image 20240626182325.png]]
> [!caution] Limited Characters
> Binary can only count up to `255` and that is the limit of the characters represented by __ASCII__


## Unicode

The generic  thumbs up emoji is `U+1F44D`.

Computer Scientists made the emojis more personalized by adding skin tones by putting another Unicode after the Unicode of the emoji like a thumbs up with a different skin tone: `U1F44D U+1F3FD`


## Colors
> [!abstract] Representation
> Red, Green, and Blue (RGB) is a combination of __Three numbers__.
> ![[Pasted image 20240626231923.png]]
> - 72 73 33 in ASCII is `H I !`
> - In colors it is a light shade of yellow.
> -  Red: 72, Green: 73, Blue: 33
> ![[Pasted image 20240626232112.png]]



## More:
> [!info]
> - Further, zeros and ones can be used to represent images, videos, and music!
> - Images are simply collections of RGB values.
> - Videos are sequences of many images that are stored together, just like a flipbook.
> - Music can be represented through MIDI data.
