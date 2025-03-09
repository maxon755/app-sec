# Homework 6. Cryptography Basics

## Task 1. Base64

The `encoding.txt` decoded with `base64` tool:

```bash
base64 -di encoded.txt > encoded
```

The decoded file is PNG image:

```bash
file decoded
decoded: PNG image data, 1410 x 595, 8-bit/color RGB, non-interlaced
```

The phrase from the image:

```txt
Задача з декодування успішно виконана

Very nice
Great success
```

## Task 2. Passwords restoring

The passwords provided in the task are cracked with `hashcat` tool and `rockyou` wordlist:

```bash
hashcat -m 0 /vagrant/passwords  /usr/share/wordlists/rockyou.txt
```

The result:

```txt
2e07a0bc2e80b76362cd738cf623a055:ilovemymom               
6adeb5f54399cec7a7178e2d48adee94:cookiemonster            
fa7667f3d3ebae421dbe05b988ac9b85:jesuslovesme             
c3669daebe306fd8ce43643ce7aa3ae9:redalert7250             
2298e5616f2a76c2e7a86cef305a8f0c:uhaveagoodjob            
8990559f2a374dac882527a86b2f6973:securityadmin284650      
43e0ab313ea599d05161f324cb5e038e:bober                    
19570fa38b775a52176561f8f70965d1:1728-apple*2533          
0062e6ff5b471a4cb65ade906ca42049:!@#$kitty!@#$            
316c33c6da18457d597efbcc3d33656d:!#7Blushing^*Bride5 
```
