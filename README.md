# 《Linux Experience for sharing with you》

> Software is like sex: It's better when it's free.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;--- The father of Linux

**Written in Front:**

The following scripts of Linux are what I have learned after class. ***BUT***, I think it's very necessary for me to share them with u. 
---

## 1. Basic Scripts for Linux
### 1.1 Dir and File Operation
**1.1.1 Operate directory**

`cd ~/linux`&nbsp;&nbsp;#  using `cd ~/file` is very convenient for entering into ***any directory***

`cd ../`&nbsp;&nbsp;#  return the directory up one level

**1.1.2. Operate file_folder & file**

***(1)***
**make** new filefolder:`mkdir file_folder1`
; **make** new file:`touch file1`

***(2)***
**copy** old filefolder:`cp -r file_folder1 file_folder2`
; **copy** old file:`cp file1 file2`

***(3)***
**rename** old filefolder:`mv file_folder2 file_folder11`
; **rename** old file:`mv file2 file11`

***(4)***
**move** file to filefolder:`mv file11 file_folder11`

***(5)***
**remove** filefolder:`rm -r filer_folder1` or `rmdir file_folder11`
; **remove** file:`rm file11`

### 1.2 View and Edit File
**1.2.1. View file**

***(1)***
**view** file directly:`cat file1`&nbsp;&nbsp;#  view all file
; **view** file added row number:`cat -n file1`&nbsp;&nbsp;#  view all file added row number

**view** file conversely:`tac file1`&nbsp;&nbsp;#  view all file conversely

***(2)***
**view file added row number:**
```
nl file1                      #  view rows including null rows
nl -b a file1                 #  view rows with null rows
nl -b a -n rz file1           #  view rows with null rows and 000... number
nl -b a -n rz -w 3 file1      #  view rows with null rows and total 3 numbers
```

***(3)***
**view file added turned pages:**
```
more file1                    #  view files and turn pages
## enter: next row; space: next page; /text: find text next;
## :f: show filename and rows; ctrl+b: turn back; q: quit

less file1                    #  view files and turn pages
## space: next page; pgdn: next page; pgdn: last page; 
## /text: find text next; ?text: find text last; q: quit
```

***(4)***
**select file:**
```
head file1                    #  select files with the first 10 rows
head -n 20 file1              #  select files with the first 20 rows
tail file1                    #  select files with the last 10 rows
tail -n 20 file1              #  select files with the last 20 rows
```

***(5)***
**edit file:**
```
cut -f 4 file                 #  get the fourth column
cut -d ";" -f 2 file          #  get the fourth column and specified as ";"
sed 's/x/X/g' file            #  replace lower-case letter with captital letter in file
sed -n 'start, end p' file    #  print columns from start to end in file 
```

```
ls -l  # check the file authority
```

## 2. Advanced Scripts for Linux


