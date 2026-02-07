# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
ajay
arya
sanjai
surya
^d
```
cat > file2
```
avi 
anjana
kaviya
swetha
^d
```
### Display the content of the files
cat < file1
## OUTPUT
```
ajay
arya
sanjai
surya
```


cat < file2
## OUTPUT
```
avi 
anjana
kaviya
swetha
```

# Comparing Files
cmp file1 file2
## OUTPUT
 ```
file1 file2 differ: byte 2, line 1
```
comm file1 file2
 ## OUTPUT
```
ajay
arya
	avi
	anjana
	kaviya
sanjai
surya
	swetha
```
 
diff file1 file2
## OUTPUT
```
1,4c1,4
< ajay
< arya
< sanjai
< surya
---
> avi
> anjana
> kaviya
> swetha
```

#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```


cut -c1-3 file11
## OUTPUT
```
Hel
Thi
```



cut -d "|" -f 1 file22
## OUTPUT
```
1001 
1002 
1003
```


cut -d "|" -f 2 file22
## OUTPUT
```
 Ram 
 tom 
 Jeo
```

cat < newfile 
```
Hello world
hello world
^d
````
cat > newfile 
Hello world
hello world
 
grep Hello newfile 
## OUTPUT
<img width="136" height="25" alt="image" src="https://github.com/user-attachments/assets/4a726866-d313-4baf-a019-ac7c36ddb3b4" />



grep hello newfile 
## OUTPUT

<img width="136" height="25" alt="image" src="https://github.com/user-attachments/assets/d521e00f-ea7c-4ac5-9269-e24d3eeb5c1f" />

grep -v hello newfile 
## OUTPUT

Hello world

cat newfile | grep -i "hello"
## OUTPUT

<img width="140" height="50" alt="image" src="https://github.com/user-attachments/assets/34d429b8-e559-4e95-a99b-98c5d467f724" />



cat newfile | grep -i -c "hello"
## OUTPUT

2


grep -R ubuntu /etc
## OUTPUT

<img width="1283" height="623" alt="image" src="https://github.com/user-attachments/assets/dcb09a25-4904-47f1-a11f-c300ca26f8af" />


grep -w -n world newfile   
## OUTPUT

<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/9b64b2f0-304c-43d6-98a3-4c0c447ffa8b" />

cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

cat > newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
egrep -w 'Hello|hello' newfile 
## OUTPUT

<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/257000d1-44db-4083-8233-7489f09ce4db" />


egrep -w '(H|h)ello' newfile 
## OUTPUT

<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/67b28081-22e3-43f8-9fea-b9453a046c0a" />


egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT

<img width="161" height="43" alt="image" src="https://github.com/user-attachments/assets/8fe7799f-4bb5-4afd-b4ac-3d8bc3048470" />



egrep '(^hello)' newfile 
## OUTPUT

<img width="161" height="28" alt="image" src="https://github.com/user-attachments/assets/6fc840e0-11d7-44ce-a4fa-8e8385211ee4" />


egrep '(world$)' newfile 
## OUTPUT

<img width="162" height="44" alt="image" src="https://github.com/user-attachments/assets/3a68dc70-2604-4cdd-80cd-39add187cad7" />


egrep '(World$)' newfile 
## OUTPUT

<img width="162" height="44" alt="image" src="https://github.com/user-attachments/assets/93ab3b5e-ad7a-41cd-9c09-1ce9a9c5576c" />


egrep '((W|w)orld$)' newfile 
## OUTPUT

<img width="316" height="69" alt="image" src="https://github.com/user-attachments/assets/af43d222-d59e-4765-a2ee-9022da45a8ff" />


egrep '[1-9]' newfile 
## OUTPUT

<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/c92e22af-c4cc-46bf-9611-7bc99f9cb077" />


egrep 'Linux.*world' newfile 
## OUTPUT
<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/16cb9f3c-f372-4bff-a9db-e4b936d5a912" />


egrep 'Linux.*World' newfile 
## OUTPUT

<img width="315" height="48" alt="image" src="https://github.com/user-attachments/assets/36f3b52c-0063-4272-945a-b0de5e08fa8b" />

egrep l{2} newfile
## OUTPUT

<img width="317" height="28" alt="image" src="https://github.com/user-attachments/assets/4bc5f8b5-15b1-499e-acc8-4d269cc64390" />


egrep 's{1,2}' newfile
## OUTPUT 
<img width="378" height="92" alt="image" src="https://github.com/user-attachments/assets/62489ed4-3ef8-4a22-ba00-aa4624d816e2" />


cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```


sed -n -e '3p' file23
## OUTPUT

1002 | tom |  5000 | Admin

sed -n -e '$p' file23
## OUTPUT

1001 | Ram | 10000 | HR

sed  -e 's/Ram/Sita/' file23
## OUTPUT

1001 | Sita | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Sita | 10000 | HR

sed  -e '2s/Ram/Sita/' file23
## OUTPUT

1001 | Ram | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR

sed  '/tom/s/5000/6000/' file23
## OUTPUT

1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  6000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR

sed -n -e '1,5p' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
```
sed -n -e '2,/Joe/p' file23
## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```

sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
```
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```
seq 10 
## OUTPUT
```
1
2
3
4
5
6
7
8
9
10
```
seq 10 | sed -n '4,6p'
## OUTPUT
```
4
5
6
```
seq 10 | sed -n '2,~4p'
## OUTPUT
```
2
3
4
```
seq 3 | sed '2a hello'
## OUTPUT
```
1
2
hello
3
```
seq 2 | sed '2i hello'
## OUTPUT
```
1
hello
2
```
seq 10 | sed '2,9c hello'
## OUTPUT
```
1
hello
10
```
sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
```
$1001 | Ram | 10000 | HR
$1001 | Ram | 10000 | HR
$1002 | tom |  5000 | Admin
```
sed -n '2,4{s/$/*/;p}' file23
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
```
#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
## OUTPUT


cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
uniq file22
## OUTPUT

<img width="664" height="236" alt="image" src="https://github.com/user-attachments/assets/482ab662-2f82-4936-9016-6d719c4d592e" />


#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT

cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
cat urllist.txt | tr -d ' '
 ## OUTPUT

v<img width="503" height="146" alt="image" src="https://github.com/user-attachments/assets/cd592648-41db-44d8-99b2-fb86a2966533" />

 
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT

<img width="645" height="145" alt="image" src="https://github.com/user-attachments/assets/58183c33-9960-4e26-bd96-1f755c1ee6be" />


#Backup commands
tar -cvf backup.tar *
## OUTPUT

<img width="708" height="734" alt="image" src="https://github.com/user-attachments/assets/f46b31e7-6293-4389-8fe3-9d0f0fce148c" />

mkdir backupdir
 
mv backup.tar backupdir

cd backupdir
 
tar -tvf backup.tar
## OUTPUT
<img width="1025" height="711" alt="image" src="https://github.com/user-attachments/assets/08bd6a72-7880-4778-92e7-9970bdda2acd" />


tar -xvf backup.tar
## OUTPUT
<img width="1016" height="715" alt="image" src="https://github.com/user-attachments/assets/779f4448-8ca8-4a41-badc-b12bed111266" />

gzip backup.tar

ls .gz
## OUTPUT
 <img width="971" height="67" alt="image" src="https://github.com/user-attachments/assets/90c9c9b5-5498-46bd-94f4-6585793f50f0" />

gunzip backup.tar.gz
## OUTPUT

 <img width="1021" height="81" alt="image" src="https://github.com/user-attachments/assets/865b88e3-d76f-4556-99e0-c597b80c469d" />

# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT

 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT


cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```

cat scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT

 
ls file1
## OUTPUT

echo $?
## OUTPUT 
./one
bash: ./one: Permission denied
 
echo $?
## OUTPUT 
 
abcd
 
echo $?
 ## OUTPUT


 
# mis-using string comparisons

cat < strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```
##OUTPUT



chmod 755 strcomp.sh
 
./strcomp.sh 
## OUTPUT


# check file ownership
cat < psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```
./psswdperm.sh
## OUTPUT

# check if with file location
cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 
```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

./ifnested.sh 
## OUTPUT

<img width="803" height="248" alt="image" src="https://github.com/user-attachments/assets/6e683cbc-a073-4e95-b0c4-1c944c5dfc86" />


# using numeric test comparisons
cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```


cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```

$ chmod 755 iftest.sh
 
$ ./iftest.sh 
##OUTPUT

# check if a file
cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```

cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

$ chmod 755 ifnested.sh
 
$ ./ifnested.sh 
##OUTPUT

# looking for a possible value using elif
cat elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 
## OUTPUT

<img width="834" height="137" alt="image" src="https://github.com/user-attachments/assets/a1d24ca8-42cb-4ada-89e6-1a35d8460180" />

# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
## OUTPUT

# using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
$ chmod 755 casecheck.sh 
 
$ ./casecheck.sh 
 
cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
$ chmod 755 whiletest.sh
 
$ ./whiletest.sh
 
 
cat untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh
 
 
 
cat forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh
 
 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh
 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
$ chmod 755 forin2.sh
 
$ ./forin2.sh 
 
cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ ./forin3.sh 
 
cat forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh

## OUTPUT
cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
$ chmod 777 forinfile.sh
$ cat cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam

## OUTPUT

<img width="906" height="195" alt="image" src="https://github.com/user-attachments/assets/cd19f222-cd03-4e37-a166-5f2f713290ac" />

cat forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````
$ chmod 755 forctype.sh
$ ./forctype.sh 
## OUTPUT

cat forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype.sh
$ ./forctype1.sh 
## OUTPUT

cat fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```
$ chmod 755 fornested1.sh
 
$ ./fornested1.sh 
 ## OUTPUT

 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```
## OUTPUT

<img width="592" height="156" alt="image" src="https://github.com/user-attachments/assets/b5963643-325d-4703-a950-2845189e659a" />

$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 
## OUTPUT
 <img width="596" height="167" alt="image" src="https://github.com/user-attachments/assets/736bdb6c-f4a1-4d81-8b77-41cb2cc2f7bd" />

cat exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
$ chmod 755 exread.sh 
 
$ ./exread.sh 
## OUTPUT

<img width="736" height="262" alt="image" src="https://github.com/user-attachments/assets/cf817af1-164b-4d51-887b-b2664ca4470a" />

 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 

## OUTPUT

<img width="498" height="193" alt="image" src="https://github.com/user-attachments/assets/c1ef7f31-1a0e-48ff-a44a-7019f1313bf9" />


$ ./exread1.sh 
 
cat funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
## OUTPUT
 ./funcex.sh 

 <img width="614" height="220" alt="image" src="https://github.com/user-attachments/assets/8a28c10d-494b-4171-96cd-426d499ad13b" />

 ./funcex.sh 1 2

 
cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh

## OUTPUT
$ ./argshift.sh 1 2 3
 <img width="365" height="119" alt="image" src="https://github.com/user-attachments/assets/126214ee-3fe3-4853-afda-c0e5858a4ac5" />

 cat argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
$ chmod 777 argshift.sh
## OUTPUT
$ ./argshift.sh 1 2 3
 <img width="512" height="119" alt="image" src="https://github.com/user-attachments/assets/bbef58e3-2376-4e2d-a945-63090515ff39" />

cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
## OUTPUT
 ./argshift.sh 1 2 3
 
 <img width="599" height="164" alt="image" src="https://github.com/user-attachments/assets/8e683943-eef0-4ca2-9e3a-84accbb91b9e" />

cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```
awk -f nc.awk data.dat
## OUTPUT 
 <img width="705" height="389" alt="image" src="https://github.com/user-attachments/assets/13d74f11-d39e-4868-94ab-30771115837d" />

cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
## OUTPUT 


# RESULT:
The Commands are executed successfully.
