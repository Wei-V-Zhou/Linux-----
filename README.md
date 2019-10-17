# 《Linux Experience for sharing with you》

> Software is like sex: It's better when it's free.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;--- The father of Linux

**Written in Front:**

The following scripts of Linux are what I have learned after class. ***BUT***, I think it's very necessary for me to share them with u. 
---

## 1. Basic Scripts for Linux
### 1.1 Dir and File Operation
**1. Operate directory**

`cd ~/linux`&nbsp;&nbsp;#  using `cd ~/file` is very convenient for entering into ***any directory***

`cd ../`&nbsp;&nbsp;#  return the directory up one level

**2. Operate file_folder & file**

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
**1. View file**

***(1)***
**view** file directly:`cat file1`&nbsp;&nbsp;#  view all file
; **view** file added row number:`cat -n file1`&nbsp;&nbsp;#  view all file added row number

**view** file conversely:`tac file1`&nbsp;&nbsp;#  view all file conversely



```
ls -l  # check the file authority
```

## 2. Advanced Scripts for Linux


