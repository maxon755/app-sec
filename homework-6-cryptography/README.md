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

## Task 2. Passwords cracking

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

## Task 3. Passwords cracking with salt

I've created the file with passwords and salt appropriate for `hashcat`:

```txt
0f47165ddcd57bc81ab4c29f65f08c9e:secureSalt###221
11a8b07ace8168c8630e529d7587b819:secureSalt###221
dc0ea26b7ce1e625d8202a4ca06136cd:secureSalt###221
d5bbca88a42402c1bfb29c22f586bf86:secureSalt###221
dfc788fa0d055f8e2a054e31a7b1fd34:secureSalt###221
70f2c284db6ec5c721473702193cf49e:secureSalt###221
dfff7f44f820f2830308dd294233ad4d:secureSalt###221
5a5c4f5f71b69dd071238bf5833a30ec:secureSalt###221
080684243d95f14ba9dc64a93f04076c:secureSalt###221
a37f32f41049a377795d106a4d5fd3ae:secureSalt###221
```

The cracked passwords:

```txt
hashcat -m 10 /vagrant/passwords-salt  /usr/share/wordlists/rockyou.txt

dfff7f44f820f2830308dd294233ad4d:secureSalt###221:peque11 
0f47165ddcd57bc81ab4c29f65f08c9e:secureSalt###221:avengers9
080684243d95f14ba9dc64a93f04076c:secureSalt###221:r3madi3 
dfc788fa0d055f8e2a054e31a7b1fd34:secureSalt###221:lorreal 
70f2c284db6ec5c721473702193cf49e:secureSalt###221:juwon101
dc0ea26b7ce1e625d8202a4ca06136cd:secureSalt###221:jballer713
a37f32f41049a377795d106a4d5fd3ae:secureSalt###221:ilovesamanderson
5a5c4f5f71b69dd071238bf5833a30ec:secureSalt###221:dube0314
11a8b07ace8168c8630e529d7587b819:secureSalt###221:dani3lz 
d5bbca88a42402c1bfb29c22f586bf86:secureSalt###221:H^7%sFm
```

`-m 10` means the `md5` algorithm applied to salted password
(the salt appended to the end)

```txt
10 | md5($pass.$salt) | Raw Hash salted and/or iterated
```
