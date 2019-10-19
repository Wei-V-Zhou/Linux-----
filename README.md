# 《Linux Experience to Share with You》

> Software is like sex: It's better when it's free.<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;--- The father of Linux

<div align=center><img src="https://github.com/Wei-V-Zhou/Linux-scripts-study/blob/master/1.jpeg" width="200" height="250" /></div>

**Written in Front:**

**"The following scripts of Linux are what I have learned after class. ***BUT***, I think it's very necessary for me to share them with u."**
<div align=center><img src="https://github.com/Wei-V-Zhou/Linux-scripts-study/blob/master/5.jpg" width="220" height="165" /></div>

---

## 1. Basic Scripts for Linux
### 1.1 Direcory and File Operation
**1.1.1 Operate directory**

`cd ~/linux`&nbsp;&nbsp;#  using `cd ~/file` is very convenient for entering into ***any directory***

`cd ../`&nbsp;&nbsp;#  return the directory up one level

`ls -l`　#　view the info of file authority: -rwx(4+2+1)-rw-r(owner-usergroup-world)

`chmod -R 765 file`　#　change the file authority

`ls -lh file`　#　view the file size;　　`wc -l file`　#　view the file rownumber

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
**view file with row number:**
```
nl file1                      #  view rows including null rows
nl -b a file1                 #  view rows with null rows
nl -b a -n rz file1           #  view rows with null rows and 000... number
nl -b a -n rz -w 3 file1      #  view rows with null rows and total 3 numbers
```

***(3)***
**view file with page turning:**
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
cut -d ";" -f 4 file          #  get the fourth column and specified as ";"
sed 's/x/X/g' file            #  replace lower-case letter with captital letter in file
sed -n 'start, end p' file    #  print columns from start to end in file 
grep 'HELLO' file             #  search every row containing HELLO in file
grep -r 'HELLO' file          #  search every row without HELLO in file
grep -w 'HELLO' file          #  search every row only with HELLO (without HELLOWORLD) in file
```

***(6)***
**arrange file:**
```
sort -k 4 file                #  sort the fourth row with ASCII character
sort -k 4 -n file             #  sort the fourth row with ASCII number
uniq -c file                  #  remove duplication and compute the value
gzip file / gunzip file.gz    #  zip/unzip file
tar -zcv -f f.tar.gz folder   #  tar folders(gzip format)
tar -ztv -f folder.tar.gz     #  view the filename of folder.tar.gz
tar -zxv -f folder.tar.gz     #  open and unzip folder.tar.gz
```
<div align=center><img src="https://github.com/Wei-V-Zhou/Linux-scripts-study/blob/master/4.jpg" width="288" height="180" /></div>

---

## 2. Advanced Scripts for Linux
### 2.1 Linux bash
*STEP1:*　`touch file1.sh`　# make a new bash file

*STEP2:*　`chmod +x file1.sh`　# add the executable authority for the bash file

*STEP3:*　edit the bash file　(e.g. our Linux homework)
```
vi file1.sh　　　　　　　　　　 #  enter the editable view mode
#!/bin/bash　　　　　　　　　　 #  state the executable sript
CUR_DIR=`ls`　　　　　　　　 　 #  get the dirname and filename list
#　clear the environment
if [ -e filename.txt ];then
        rm filename.txt
fi
if [ -e dirname.txt ];then
        rm dirname.txt
fi
#　for loop to read the dirname and filename
for val in $CUR_DIR
do
        # Output dirname
        if [ -d $val ];then
                echo "Dir: $val" >> dirname.txt
        # Output filename
        elif [ -f $val ];then
                echo "File: $val" >> filename.txt
        fi
done

exit 0
```

### 2.2 Control structure

**2.2.1. if sentence**
```
if [condition1]; then
command1
elif [condition2]; then
command2
else
command3
fi
```
**[condition]:** `-f filename`　#decide whether it is file;　`-d dirname`　#decide whether it is directory;　`-e file`　#decide whether exists file;　`-n file`　#decide whether file is not empty;　`-z file`　#decide whether file is empty;　`-eq`　#equal;　`-ne`　#not equal;　`-gt`　#greater than;　`-ge`　#greater than or equal to;　`-lt`　#less than;　`-le`　#less than or equal to

**2.2.2. for sentence**
```
for var in $list
do
command1
command2
done
```
**[command]:** `echo $val`　#print val;　`echo $val > file.txt`　#write file totaly;　`echo $val >> file.txt`　#write file after the tail

### 2.3 Advanced sentence
```
docker exec -it bioinfo_tsinghua bash           #enter docker
docker exec -it -u root contain_name bash　     #enter root mode
su test　　　　　　　　　　　　　　　　　　        #enter test mode
docker cp contain_name:/home/test/file C:\dir   #copy file to your computer
docker cp C:\...\file contain_name:/home/test   #copy file to your virtualbox
ls dir -F | grep "/$"                 　        #show folder
ls -al | grep "^d"                              #show folder
ls -al | grep "^_"                              #show file
awk 'pattern{commands}'                         #word editing and processing
grep exon 1.gtf | awk '{print $5-$4+1}'|sort -n|tail -3 > 1.txt　　
#search exon in 1.gtf, print the length, sort by number, get the last 3 rows and output it to 1.txt
cat 1.gtf | awk '$3=="gene"{split($10, genename, ";"); name = genename[1]; gsub("\"", "", name);print name, $5-$4+1}' | head
#get file 1.gtf, find the gene rows, split the 10th column by ";", get the first in the splited array, replace the " and print the first 10 rows
```
However, I think the most fluent sentences we used are as follows:

`clear`,　`exit`, or `docker exec -it bioinfo_tsinghua bash`...
<div align=center><img src="https://github.com/Wei-V-Zhou/Linux-scripts-study/blob/master/7.jpg" width="300" height="192" /></div>

---
## THANKS FOR YOUR LISTENING!!!
>Welcome to my github webpage [Wei-V-Zhou](https://github.com/Wei-V-Zhou) for further discussion
