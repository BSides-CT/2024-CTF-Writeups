# Web

## If You Give a Mouse a Cookie
I just baked a fresh batch of cookies and now they're all gone!!

Can you investigate?

**Author:** boom

### Solution
Go to the webpage we had setup during the CTF, open your browser's developer tools by inspecting the page, navigate to the `Network` tab and refresh the page.

Under the cookies of the page there is:

`request=QlNJREVTQ1R7bjBtX24wbV9uMG1fczBfeXVtbXkhfQ==`

Decode from base64 to get the flag.

### Flag
> `BSIDESCT{n0m_n0m_n0m_s0_yummy!}`


## Restricted Access
Greetings, carbon-based lifeform. I am your friendly neighborhood web crawler, and I have encountered a digital obstacle that you must overcome. Your mission, should you choose to accept it, involves a file that is typically off-limits to my kind. Thank you kindly, human!

**Author:** boom

### Solution
Go to `ctf.bsidesct.org/robots.txt` to get the flag

### Flag
> `BSIDESCT{b33p_b00p!}`


## Lost and Found
ERROR! ERROR! ERROR! WE CAN'T FIND THE FLAG!

**Author:** boom

### Solution
Just hit the 404 page for `bsidesct.org` and you will find the flag in the HTML

### Flag
> `BSIDESCT{404_n0t_f0und_but_fl4g_w4s?}`


## Stick to the script
And not in like a Stanley Kubrick or Alfred Hitchcock yelling at their cast kind of way.

**Author:** boom (shoutout to Perfidious for coming up with the name of this one)

### Solution
Inspect the webpage at `bsidesct.org`, navigate to the `Console` tab and the flag is revealed if you scroll up a little bit

### Flag
> `BSIDESCT{why_is_this_in_the_javascript?}`


## Footloose
Keep scrolling... keep scrolling... keep scrolling... and you probably got to where the flag is. Maybe? Hopefully? Eventually. Just keep digging once you find it on the webpage.

**Author:** boom

### Solution
If you went to the bottom of the homepage of `bsidesct.org` there was a small BSidesCT logo at the footer of the page.

From there, you were to inspect the image a bit. Using `steghide extract` would reveal there was something in the file, however, it was protected with a password.

You then needed to bruteforce it using `rockyou.txt` to obtain `hmmm.txt` which was hidden in the image. The password was `0124309682`

You could use StegCracker to do the bruteforce: https://github.com/Paradoxis/StegCracker

The command for this one was `steghide extract -sf logo.jpg` once you got the password

This challenge wasn't very practical, however, I thought it was a fun challenge. Although, hints should have been released a little earlier in the day.

### Flag
> `BSIDESCT{w3b_0r_st3g_i_dunn0}`