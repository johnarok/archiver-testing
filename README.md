# archiver-testing
WIP artifacts for archiver testing 

Windows to Windows
```
C:\Users\user01\go\src\test>archiver.exe open testdata-windows.zip

C:\Users\user01\go\src\test>dir .\testdata

 Directory of C:\Users\user01\go\src\test\testdata

11/03/2018  08:33 PM    <DIR>          .
11/03/2018  08:33 PM    <DIR>          ..
11/03/2018  08:33 PM             8,944 already-compressed.jpg
11/03/2018  08:33 PM                 0 exist
11/03/2018  08:33 PM                 0 proverb3.txt
11/03/2018  08:33 PM    <DIR>          proverbs
11/03/2018  08:33 PM                58 quote1.txt
               4 File(s)          9,002 bytes
               3 Dir(s)  200,142,626,816 bytes free
```

Windows to Windows
```
C:\Users\user01\go\src\test>archiver.exe open testdata-windows.tar

C:\Users\user01\go\src\test>cd testdata

C:\Users\user01\go\src\test\testdata>dir

 Directory of C:\Users\user01\go\src\test\testdata

11/03/2018  07:38 PM    <DIR>          .
11/03/2018  07:38 PM    <DIR>          ..
11/03/2018  07:38 PM             8,944 already-compressed.jpg
11/03/2018  07:38 PM    <SYMLINK>      exist [testdata\exist]
11/03/2018  07:38 PM    <SYMLINK>      proverb3.txt [testdata\proverb3.txt]
11/03/2018  07:38 PM    <DIR>          proverbs
11/03/2018  07:38 PM                58 quote1.txt
               4 File(s)          9,002 bytes
               3 Dir(s)  200,148,697,088 bytes free
```

Linux to Windows
```
C:\Users\user01\go\src\test>archiver.exe open testdata-linux.zip

C:\Users\user01\go\src\test>dir .\testdata

 Directory of C:\Users\user01\go\src\test\testdata

11/03/2018  08:29 PM    <DIR>          .
11/03/2018  08:29 PM    <DIR>          ..
11/03/2018  08:29 PM             8,944 already-compressed.jpg
11/03/2018  08:29 PM                22 exist
11/03/2018  08:29 PM                27 proverb3.txt
11/03/2018  08:29 PM    <DIR>          proverbs
11/03/2018  08:29 PM                58 quote1.txt
               4 File(s)          9,051 bytes
               3 Dir(s)  200,142,331,904 bytes free
```

Linux to Windows
```
C:\Users\user01\go\src\test>archiver.exe open testdata-linux.tar

C:\Users\user01\go\src\test>dir .\testdata

 Directory of C:\Users\user01\go\src\test\testdata

11/03/2018  08:30 PM    <DIR>          .
11/03/2018  08:30 PM    <DIR>          ..
11/03/2018  08:30 PM             8,944 already-compressed.jpg
11/03/2018  08:30 PM    <SYMLINK>      exist [\target\does\not\exist]
11/03/2018  08:30 PM    <SYMLINK>      proverb3.txt [proverbs\extra\proverb3.txt]
11/03/2018  08:30 PM    <DIR>          proverbs
11/03/2018  08:30 PM                58 quote1.txt
               4 File(s)          9,002 bytes
               3 Dir(s)  200,142,315,520 bytes free
```

Linux to Linux
```
 $ archiver open ./testdata-linux.zip
$ ls -ltr ./testdata
total 20
-rw-r--r-- 1 user01 user01   58 Nov  3 20:06 quote1.txt
drwxr-xr-x 3 user01 user01 4096 Nov  3 20:06 proverbs
lrwxrwxrwx 1 user01 user01   27 Nov  3 20:06 proverb3.txt -> proverbs/extra/proverb3.txt
lrwxrwxrwx 1 user01 user01   22 Nov  3 20:06 exist -> /target/does/not/exist
-rw-r--r-- 1 user01 user01 8944 Nov  3 20:06 already-compressed.jpg
```

Linux to Linux
```
$ archiver open ./testdata-linux.tar
$ ls -ltr ./testdata
total 20
-rw-r--r-- 1 user01 user01   58 Nov  3 20:45 quote1.txt
drwxr-xr-x 3 user01 user01 4096 Nov  3 20:45 proverbs
lrwxrwxrwx 1 user01 user01   27 Nov  3 20:45 proverb3.txt -> proverbs/extra/proverb3.txt
lrwxrwxrwx 1 user01 user01   22 Nov  3 20:45 exist -> /target/does/not/exist
-rw-r--r-- 1 user01 user01 8944 Nov  3 20:45 already-compressed.jpg
```

Windows to Linux
```
 $ archiver open ./testdata-windows.zip
/home/user01/testdata/exist: making symbolic link for: symlink  /home/user01/testdata/exist: no such file or directory
```

Windows to Linux
```
$ archiver open ./testdata-windows.tar
$ ls -ltr ./testdata
total 20
-rw-rw-rw- 1 user01 user01   58 Nov  3 20:11 quote1.txt
drwxr-xr-x 3 user01 user01 4096 Nov  3 20:11 proverbs
lrwxrwxrwx 1 user01 user01   21 Nov  3 20:11 proverb3.txt -> 'testdata\proverb3.txt'
lrwxrwxrwx 1 user01 user01   14 Nov  3 20:11 exist -> 'testdata\exist'
-rw-rw-rw- 1 user01 user01 8944 Nov  3 20:11 already-compressed.jpg
```
