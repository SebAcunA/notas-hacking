#### Descripción 
Every file gets a flag.The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/258/flag.png).
#### Solución
```
┌──(kali㉿kali)-[~/forensic/hideme]
└─$ zsteg -a flag.png                                                      
[?] 3198 bytes of extra data after image end (IEND), offset = 0x9b3b
extradata:0         .. file: Zip archive data, made by v3.0 UNIX, extract using at least v1.0, last modified Mar 16 2023 02:01:50, uncompressed size 0, method=store
    00000000: 50 4b 03 04 0a 00 00 00  00 00 39 10 70 56 00 00  |PK........9.pV..|
    00000010: 00 00 00 00 00 00 00 00  00 00 07 00 1c 00 73 65  |..............se|
    00000020: 63 72 65 74 2f 55 54 09  00 03 8d 78 12 64 8d 78  |cret/UT....x.d.x|
    00000030: 12 64 75 78 0b 00 01 04  00 00 00 00 04 00 00 00  |.dux............|
    00000040: 00 50 4b 03 04 14 00 00  00 08 00 39 10 70 56 0f  |.PK........9.pV.|
    00000050: 5a d1 78 3c 0b 00 00 d5  0b 00 00 0f 00 1c 00 73  |Z.x<...........s|
    00000060: 65 63 72 65 74 2f 66 6c  61 67 2e 70 6e 67 55 54  |ecret/flag.pngUT|
    00000070: 09 00 03 8d 78 12 64 8d  78 12 64 75 78 0b 00 01  |....x.d.x.dux...|
    00000080: 04 00 00 00 00 04 00 00  00 00 cd 56 55 5c d3 8d  |...........VU\..|
    00000090: 1a fe 83 0a a3 27 48 7c  84 80 94 32 7a 12 32 a9  |.....'H|...2z.2.|
    000000a0: 09 92 03 1c 29 21 21 30  69 a4 26 35 40 42 90 54  |....)!!0i.&5@B.T|
    000000b0: 3f 44 40 24 86 c0 a8 d1  08 23 94 10 46 c8 87 12  |?D@$.....#..F...|
    000000c0: d2 18 1b 63 a4 92 92 67  e7 dc 9d 8b 73 7f de 8b  |...c...g....s...|
    000000d0: 37 9f f7 e6 f9 3d ef ef  f7 26 9b 9b ea b3 31 f3  |7....=...&....1.|
    000000e0: 33 03 00 c0 66 68 a0 8b  04 00 7a 5b 5a ae 04 a6  |3...fh....z[Z...|
    000000f0: 39 60 d7 57 d2 9a 16 ce  a3 74 10 3a 00 50 97 c1  |9`.W.....t.:.P..|
chunk:0:IHDR        .. file: Adobe Photoshop Color swatch, version 0, 512 colors; 1st RGB space (0), w 0x1f8, x 0x806, y 0, z 0; 2nd RGB space (0), w 0, x 0, y 0, z 0
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/forensic/hideme]
└─$ binwalk -e flag.png

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
41            0x29            Zlib compressed data, compressed
39739         0x9B3B          Zip archive data, at least v1.0 to extract, name: secret/
39804         0x9B7C          Zip archive data, at least v2.0 to extract, compressed size: 2876, uncompressed size: 3029, name: secret/flag.png

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/forensic/hideme]
└─$ ls
flag.png  _flag.png.extracted
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/forensic/hideme]
└─$ ls _flag.png.extracted/                 
29  29.zlib  9B3B.zip  secret
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/forensic/hideme]
└─$ strings secret/flag.png | grep -i "pico"
strings: 'secret/flag.png': No such file
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/forensic/hideme]
└─$ cd _flag.png.extracted/secret/
ls
strings flag.png | grep -i "pico"
exiftool flag.png
flag.png
ExifTool Version Number         : 13.36
File Name                       : flag.png
Directory                       : .
File Size                       : 3.0 kB
File Modification Date/Time     : 2023:03:15 22:01:49-04:00
File Access Date/Time           : 2026:03:30 03:57:24-04:00
File Inode Change Date/Time     : 2026:03:30 03:55:05-04:00
File Permissions                : -rw-r--r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 600
Image Height                    : 50
Bit Depth                       : 16
Color Type                      : Grayscale
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Gamma                           : 2.2
White Point X                   : 0.3127
White Point Y                   : 0.329
Red X                           : 0.64
Red Y                           : 0.33
Green X                         : 0.3
Green Y                         : 0.6
Blue X                          : 0.15
Blue Y                          : 0.06
Background Color                : 65535
Modify Date                     : 2023:03:16 02:01:49
Warning                         : [minor] Text/EXIF chunk(s) found after PNG IDAT (may be ignored by some readers) [x2]
Datecreate                      : 2023-03-16T02:01:49+00:00
Datemodify                      : 2023-03-16T02:01:49+00:00
Image Size                      : 600x50
Megapixels                      : 0.030
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/forensic/hideme/_flag.png.extracted/secret]
└─$ ls                            
flag.png
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/forensic/hideme/_flag.png.extracted/secret]
└─$ xdg-open flag.png  

picoCTF{Hiddinng_an_imag3_within_@n_ima9e_d55982e8} en la imagen

```
#### Notas
este reto es bastante rebuscado pero se logró encontrar la bandera
#### Referencias
