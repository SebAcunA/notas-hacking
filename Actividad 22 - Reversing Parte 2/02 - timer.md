#### Descripción 
You will find the flag after analysing this apkDownload [here](https://artifacts.picoctf.net/c/449/timer.apk).
#### Solución
```
┌──(kali㉿kali)-[~/picoctf/reversing/time]
└─$ apktool -d timer.apk
Apktool v2.7.0-dirty - a tool for reengineering Android apk files
with smali v2.5.2.git2771eae-debian and baksmali v2.5.2.git2771eae-debian
Copyright 2010 Ryszard Wiśniewski <brut.alll@gmail.com>
Copyright 2010 Connor Tumbleson <connor.tumbleson@gmail.com>

usage: apktool
 -advance,--advanced   prints advance information.
 -version,--version    prints the version then exits
usage: apktool if|install-framework [options] <framework.apk>
 -p,--frame-path <dir>   Stores framework files into <dir>.
 -t,--tag <tag>          Tag frameworks using <tag>.
usage: apktool d[ecode] [options] <file_apk>
 -f,--force              Force delete destination directory.
 -o,--output <dir>       The name of folder that gets written. Default is apk.out
 -p,--frame-path <dir>   Uses framework files located in <dir>.
 -r,--no-res             Do not decode resources.
 -s,--no-src             Do not decode sources.
 -t,--frame-tag <tag>    Uses framework files tagged by <tag>.
usage: apktool b[uild] [options] <app_path>
 -f,--force-all          Skip changes detection and build all files.
 -o,--output <dir>       The name of apk that gets written. Default is dist/name.apk
 -p,--frame-path <dir>   Uses framework files located in <dir>.

For additional info, see: https://ibotpeaches.github.io/Apktool/ 
For smali/baksmali info, see: https://github.com/JesusFreke/smali
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/reversing/time]
└─$ apktool d timer.apk 
I: Using Apktool 2.7.0-dirty on timer.apk
I: Loading resource table...
I: Decoding AndroidManifest.xml with resources...
I: Loading resource table from file: /home/kali/.local/share/apktool/framework/1.apk
I: Regular manifest package...
I: Decoding file-resources...
I: Decoding values */* XMLs...
I: Baksmaling classes.dex...
I: Baksmaling classes3.dex...
I: Baksmaling classes2.dex...
I: Copying assets and libs...
I: Copying unknown files...
I: Copying original files...
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/reversing/time]
└─$ ls
timer  timer.apk
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/reversing/time]
└─$ cd timer
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/reversing/time/timer]
└─$ grep -rni "pico{"                               
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/reversing/time/timer]
└─$ grep -rni "picoCTF"
smali_classes3/com/example/timer/BuildConfig.smali:15:.field public static final VERSION_NAME:Ljava/lang/String; = "picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}"
apktool.yml:64:  versionName: picoCTF{t1m3r_r3v3rs3d_succ355fully_17496}
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/picoctf/reversing/time/timer]
└─$ 

```
#### Notas
#### Referencias
