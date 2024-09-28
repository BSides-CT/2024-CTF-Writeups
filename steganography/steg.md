# Steganography

## Black Hole
Welp I had a challenge made, but a black hole came and messed it all up. Maybe see if you can still get the flag from it?

**Author:** boom

### Solution

Need to either use this command `hexdump -v -e '1/4 "%08x"' -e '"\n"' black_hole | xxd -r -p > output_file.jpg` or write a script to help solve. Basically the endianness is swapped

Using `exiftool` you see there is an error related to JPEG, which would be a good path to then take in terms of where to look next

When using `ghex` or any other hex editor, you'd see endianness is swapped

Alternatively this could be solved easily in CyberChef by doing `To Hex > Swap Endianness > Render Image`

### Flag
> `BSIDESCT{damn_you_black_hole!}`


## Dark Side of the Moon
Ah, the sound sweet space whispers hitting your ear as you play this audio. Since sound waves don't travel in space.. maybe they're hidden in this audio file somewhere? 

**Author:** boom

### Solution

Use QSSTV on Linux or something similar to decode from a `.wav` file to a `.bmp` or any image really to get the flag.

This is a guided tutorial on using QSSTV to achieve said results:

 https://ourcodeworld.com/articles/read/956/how-to-convert-decode-a-slow-scan-television-transmissions-sstv-audio-file-to-images-using-qsstv-in-ubuntu-18-04

The image was a little picture I drew on MS Paint so I hope those who solved it enjoyed the art :)

### Flag
> `BSIDESCT{n0w_y0u_kn0w_4b0ut_sstv}`


## Gloop Gleeb
So unfortunately for us, some aliens came down the other day and replaced the challenge file with a clip of their weird gibberish. But fortunately for you, you get to find the flag and get some points! It's a win-win **however you look at it**.

**Author:** boom

### Solution

Open the `.wav` file in Audacity and go to Spectrogram view and the flag is shown. Apologies for the bad handwriting it is hard with a mouse :p

### Flag
> `BSIDESCT{hunt_th3m_fr3qu3nc135}`

## The Next Rick Rubin
“Look for what you notice but no one else sees.” - Rick Rubin

**Author:** boom

### Solution
Run the `.wav` file through a decoder and you are left with binary. Then convert that binary to text and you get the flag.

This is a really helpful decoder: https://morsecode.world/international/decoder/audio-decoder-adaptive.html

### Flag
> `BSIDESCT{b0y_d0_1_l0v3_d0t5_4nd_d4sh35}`


## Looking through the Windows
Dig deep into your online toolshed to solve this one!

**Author:** Haptekz

### Solution
Run `challenge.png` through something like https://manytools.org/hacker-tools/steganography-encode-text-into-image/ to decode and you are given the flag.

### Flag
> `BSIDESCT{photobomb}`