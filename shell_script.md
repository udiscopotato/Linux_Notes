### Find Shell
- echo $0 (current shell)
- cat /etc/shells (available shells)
- cat /etc/passwd (your default shell)

### variable declaration:
- var1="value"  (this will take straight value)
- var2=$(command) or `command`  (this will take output of command as value)
- var3=$1   (this will take first command option as value)
- read var4    (this will take input from user and store in "var4" variable)
- read -p "enter a number" var5   (this will show a prompt)
- var6=$(( var1 + var2))   (arithmatic operation as value)

### to check exit code $?=0   or $? -eq 0

## Operators
- Arithmetic Operators: (+,-,*,/,%,++,--)
- 
### File Test Operators
- -e: Checks if the file exists.
- -f: Checks if the file is a regular file (not a directory or device file).
- -d: Checks if the file is a directory.
- -s: Checks if the file size is greater than zero.
- -r: Checks if the file is readable.
- -w: Checks if the file is writable.
- -x: Checks if the file is executable.

## Statements
### ifelse or ifelifelse
```javascript
if [ condition1 ]
then
    do-this
elif [ condition2 ]
then
    do-this
else
    do-this
fi
```

### for-loop
```javascript
for a in {1..n}
do
    echo $a
done
```
```javascript
for b in name1 name2 name3 name4 name5
do
    echo $b
done
```
### Advanced for-loops
```javascript
for ((i=1; i<=10; i++))
do
   echo "Number: $i"
done

```
```javascript
for i in $(ls)
do
   echo "File: $i"
done

```
```javascript
array=("element1" "element2" "element3")
for i in "${array[@]}"
do
   echo "Element: $i"
done
```
```javascript
LIMIT=10
for ((a=1, b=1; a <= LIMIT ; a++, b++))
do
   echo "$a-$b"
done
```

### while-loop
```javascript
i=5
while [ $i -gt 0 ]
do
   echo "Countdown ends in $i..."
   ((i--))
   sleep 1
done
echo "Countdown is over!"
```
### Advance while-loop
```javascript
i=1
while [ $i -gt 0]
do
   echo "Countdown to infinity: $i..."
   ((i++))
   sleep 0.1s
done
```
```javascript
file=temp.txt
while read -r line
do
   echo $line
done < "$file"
```
```javascript
i=0
while [ $i -le 10 ]
do
   ((i++))
   if [ $i -eq 5 ]
   then
      continue
   fi
   if [ $i -gt 8 ]
   then
      break
   fi
   echo "Number: $i"
done
```

### case-statement
```javascript
day=$(date +%A)

case $day in
    Monday)
        echo "It's Monday!";;
    Tuesday|Wednesday|Thursday)
        echo "It's a weekday.";;
    Friday)
        echo "TGIF!";;
    Saturday|Sunday)
        echo "It's the weekend!";;
    *)
        echo "Unknown day.";;
esac
```


More examples are present in :
https://github.com/udiscopotato/bash-scripting-all