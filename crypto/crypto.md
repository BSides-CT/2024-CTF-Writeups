# Cryptography

## Crypto Mania
Hackers have robbed The First Bank of Telsa and were arrested, hardware and drives recovered however, we have obtained access to one of their cloud drives that hold access to the funds. We have found a string that we believe is a password found in krypto.wallet but it needs a key to decrypt can you help us? 

`UlZaTVIwaFdSbGQ3UWpONFgzcHNiMjlmY1RaNU5uVmZTV3hxZUhWb1gzQTJYek40ZDMwPQ==`

**Author:** Joshua Ragland

### Solution

It is double Base64 encoded. You can use CyberChef or any other decoder to decode it twice.

You will be left with: EVLGHVFW{B3x_zloo_q6y6u_Iljxuh_p6_3xw}

From there, brute forcing using Caesar's Cipher would leave you with: BSIDESCT{Y3u_will_n6v6r_Figure_m6_3ut}

And last, just decode the leet speak

### Flag
> `BSIDESCT{Y0u_will_n3v3r_Figure_m3_0ut}`


## Is this the industry-leading cert?
I heard recruiters on LinkedIn talking about how they want applicants to have "industry-leading" certs like the OSCP and CISSP. Is this somewhat similar to that?

Surely the flag has to be somewhere in here.. right?

**Author:** boom


### Solution
You just need to read out the file using `openssl req -in flag.csr -noout -text`

From there, there is a fake field next to `CN` named `RSA` where the value is Base92. Converting from Base92 you get the flag.

### Flag
> `BSIDESCT{d3f_n0t_0$cp_0r_C155P}`


## Party Like It's 100 BC
The greatest enemy will hide in the last place you would ever look.

**Author:** boom

### Solution

Just Caesar's Cipher is used here

### Flag
> `BSIDESCT{c43s4r_my_b3l0v3d}`


## You can encode using condiments now?
So I just found out you can encode using "vinegar" cipher now? That's crazy. Talk about a sour twist in encryption, eh?

`WAVHKSTO{zrh_ciez_we_fgljvuvg?}`

**Author:** boom

### Solution
Decode using Vignere Cipher for this one

### Flag
> `BSIDESCT{red_wine_or_balsamic?}`