# OSINT

## The Fill n Chill
The Fill N Chill in Massachusetts has a current Diesel fuel tank temperature of what?

**Flag format:** `BSIDESCT{xx.xx}`

**Author:** John C

### Solution
Using Shodan to search for "Fill n Chill" will lead you to the flag

https://www.shodan.io/search?query=fill+n+chill

Alternatively, you can do what one group did and social engineer the gas station over the phone to give you the flag. Shoutout to them!

### Flag
The temperature updated in the afternoon so there were two flags:

> Morning: `BSIDESCT{69.70}`

> Afternoon: `BSIDESCT{69.66}`


## Find the Freeman
The user `The-Freeman921` of a particular website has a Proton Mail account, when was it created?

Format: YYYY-MM-DD

**Author:** John C

### Solution
Use the username with a tool like `WhatsMyName` or something similar to find a GitHub account with a repo consisting of PGP keys. Then, use a tool like `Kleopatra` to find the email linked to the PGP key and then use a tool like `Protosint` to find the creation date of the account.

### Flag
Depending on how you solved this, there were two flags:

> `BSIDESCT{2024-09-03}`

> `BSIDESCT{2024-09-04}`


## Back in my day..
Back before the **2008** recession, I saw this really nice picture of the animatronic, Clover the Cow, from Stew Leonards somewhere on an old photo sharing site..

However, I lost track of where it was. I am curious what camera model was used to take the picture(s). 

Can you find that for me?

**Author:** boom

### Solution
Some simple Google dorking for `"stew leonards animatronics"` would yield you a Flickr gallery containing an image of Clover the Cow. On the right of the page under the image, the camera model can be found.

https://www.flickr.com/photos/hectic/526708027/in/photostream/

### Flag
> `BSIDESCT{PowerShot G3}`

> `BSIDESCT{Canon PowerShot G3}`