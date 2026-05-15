#### Descripción 
Python scripts are invoked kind of like programs in the Terminal...
Can you run [ende.py](https://challenge-files.picoctf.net/c_wily_courier/d8ab9bfd6822fadbdfa9faffb487dab337afaf8c83d447a1b954373e15bc7d7e/ende.py) using [password.txt](https://challenge-files.picoctf.net/c_wily_courier/d8ab9bfd6822fadbdfa9faffb487dab337afaf8c83d447a1b954373e15bc7d7e/password.txt) to get [flag.txt.en](https://challenge-files.picoctf.net/c_wily_courier/d8ab9bfd6822fadbdfa9faffb487dab337afaf8c83d447a1b954373e15bc7d7e/flag.txt.en)?
#### Solución
``` 
rosyperez@MacBookAir PythonWrangLing % pip3 install cryptography
Defaulting to user installation because normal site-packages is not writeable
Collecting cryptography
  Downloading cryptography-48.0.0-cp39-abi3-macosx_10_9_universal2.whl (8.0 MB)
     |████████████████████████████████| 8.0 MB 1.6 MB/s 
Collecting cffi>=2.0.0
  Using cached cffi-2.0.0-cp39-cp39-macosx_11_0_arm64.whl (180 kB)
Collecting typing-extensions>=4.13.2
  Using cached typing_extensions-4.15.0-py3-none-any.whl (44 kB)
Collecting pycparser
  Using cached pycparser-2.23-py3-none-any.whl (118 kB)
Installing collected packages: pycparser, typing-extensions, cffi, cryptography
Successfully installed cffi-2.0.0 cryptography-48.0.0 pycparser-2.23 typing-extensions-4.15.0
WARNING: You are using pip version 21.2.4; however, version 26.0.1 is available.
You should consider upgrading via the '/Library/Developer/CommandLineTools/usr/bin/python3 -m pip install --upgrade pip' command.
rosyperez@MacBookAir PythonWrangLing % python3 ende.py -d flag.txt.en 720b6ad346f84cd483c60c7464dd95d4
picoCTF{4p0110_1n_7h3_h0us3_9c5f9bcf}
rosyperez@MacBookAir PythonWrangLing %
```
#### Notas
#### Referencias