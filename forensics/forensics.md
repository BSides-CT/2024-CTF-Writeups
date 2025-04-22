# Forensics

## -sV -sC
Feels like I'm doing HackTheBox again... 

**Flag Format:** Put the ports in ascending order separated by commas ie. `BSIDESCT{123,443,3389}`

**Author:** chicora

### Solution
Use this filter to see SYN/ACK packets and open ports:

`tcp.flags.ack ==1 && tcp.flags.syn ==1` 

Export the filtered results to a CSV file, copy Info column to new sheet, use text to columns using spaces, you should now have a column of all the open ports, dedupe and sort low to high.

### Flag
> `BSIDESCT{21,22,79,80,139,445,8000,12000}`


## Super Secure Hacking
What version of Super Hacker Hacking is present?

Moving forward, use the same pcap file from the previous challenge. I didn't want to make you keep redownloading the same file :)

**Author:** chicora

### Solution
Filter on `ssh` in Wireshark, follow the TCP stream, flag is Base64 encoded

### Flag
> `BSIDESCT{OpenSSHFlag}`


## Finger
This almost reminds me of an urban plan from 1947 which provides a strategy for the development of the Copenhagen metropolitan area, Denmark. According to the plan, Copenhagen is to develop along five 'fingers', centered on S-train commuter rail lines, which extend from the 'palm', that is the dense urban fabric of central Copenhagen!

**Author:** chicora

### Solution
Filter on `finger` in Wireshark, follow the TCP stream, flag is in binary

### Flag
> `BSIDESCT{PCAP-FingerPlanFlag!}`


## Server Message Block?
Hmm... you're telling me there are shares of SMB? What stock ticker is that?

**Author:** chicora

### Solution
Filter on `smb2` in Wireshark, follow a response TCP stream, the flag is Base58 encoded and the share name has periods between each letter that have to be removed before decoding

### Flag
> `BSIDESCT{PCAP-SMB-Shares}`


## anonymous;anonymous[@]bsidesct.org
Hopefully our network admin changed the default creds here :/

**Author:** chicora

### Solution
Filter `ftp` In Wireshark, there’s a hydra brute scan running, go to `Edit > Find Packet > Search` for the string “successful”

### Flag
> `BSIDESCT{redskins}`


## I hope this isn't a ZIP bomb..
Looks like someone sent a zip file. Hopefully it isn't a ZIP bomb..

Can you check it out?

**Author:** chicora

### Solution
In Wireshark go to `File > Export Objects > HTTP > Change the Content Type drop down to “applicaiton/zip”` and download `file.zip`. Then run these commands:
- `zip2john file.zip > crackzip`
- `johnjohn -wordlist:/usr/share/wordlists/rockyou.txt  crackzip`
- `unzip file.zip` (Password is football23)
- `cat flag.txt`

### Flag
> `BSIDESCT{PCAP_Export_ZipFile}`


## Gateway to the Big MAC
Like Harold & Kumar on their way to White Castle, only this time it's you finding a particular MAC address :)

**Author:** chicora

### Solution
- Method 1: Filter by `icmp` in Wireshark, look for pings from the computer to the gateway
- Method 2: Knowing the IP subnet is 192.168.55.0/24 filter by `ip.dst == 192.168.55.1`
- From there look for Destination MAC in the packets

### Flag
> `BSIDESCT{00:15:17:BE:7B:41}`


## Drop the S
What screams "I'm insecure?"

`http://`

**Author:** chicora

### Solution
One method is to go to `File > Export Objects > HTTP > choose “text/html” from Content Type > Filter by Size`. 

Since nikto was running while connecting with the browser with the flag in the User Agent a lot of the files are 276 bytes you'll need to filter out the noise from the scan.

The flag is in a request for `index.html` in packet 1173 and encoded with Base64

### Flag
> `BSIDESCT{User_Agent_PCAP_Flag}`


## Joint Photographics Experts Group
I love pictures. They hold so many memories and potentially even more than that!

**Author:** chicora

### Solution
In Wireshark go to `File > Export Objects > HTTP > choose “image/jpeg” > save pcap.jpg`

Then look at the exif data for the flag encoded in Base58


### Flag
> `BSIDESCT{PCAP_EXIF_JPG_FLAG}`


## Rsync
Like a threat actor about to exfil your organization's data!

**Author:** chicora

### Solution
Knowing rsync runs on port 12000 (also in port scan) filter on that port with `tcp.port == 12000` and then follow the TCP stream on a packet for the flag in Base32

### Flag
> `BSIDESCT{PCAP-RSYNC-FLAG-FOUND!!!!}`


## Recursiveness? More like RecursiveMESS
Why did the recursive programmer get kicked out of the bar? Because he kept asking for “one more round… just one more... just one more... just one more... just one more... just one more!"

**Author:** boom

### Solution
A simple way to solve this is with this one liner: `grep -r -h 'BSIDESCT{' | sort | uniq -c`

The flag was found in this directory:
```
/flag/flags/flag_9774/flag_8682/flag_1746
/flag_5099/flag_369/flag_5380/flag_7701
/flag_414/flag_3426/flag_4610/flag_3041
/flag_3097/flag_9926/flag_9205/flag_8849
/flag_8676/flag_2995/flag_1164/flag_8960
/flag_2633/flag_3341/flag_4635/flag_180
/flag_9684/flag_3111/flag.txt
```

### Flag
> `BSIDESCT{grep_and_uniq_my_beloved}`

