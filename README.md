# MacAddress_Spoof
Just a line of code heavily borrowed off the folks at https://www.igeeksblog.com/how-to-find-and-change-mac-address-on-mac/ just an alias for your bash profile so you can easily call it whenever you need it for (i) the slightly illegitimate purpose of getting another hour of free wifi or (ii) the slightly more legitimate purpose of security

Just drop `alias spoof_mac='ifconfig en0; openssl rand -hex 6 | sed "s/\(..\)/\1:/g; s/.$//" | xargs sudo ifconfig en0 ether; ifconfig en0'` into your ~/.bash_profile on a Mac OSX machine (confirmed to work on Sierra 10.12.6).

Call from the command line with `spoof_mac` preferably while disconnected from networks but with wifi on. There should be a different mac address reported in the before and after ifconfig prints. Make sure that en0 is indeed your wifi (and not some other network device, wifi might be en1 on your machine).

Happy spoofing!
