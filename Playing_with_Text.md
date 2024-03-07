## Filters/Text Processors Commands
There're some commands which gives linux many power to process texts.i.e.
- cut
- awk
- grep and egrep
- sort
- uniq
- wc

### cut (Text Processor Command)
- Cut is a command line utility that allows you to cut parts of a lines from specific file or piped data and print the result to standard output. It can be used to cut lines by delimiter, byte position and character.
- cut -c1 filename  (print first character of each line)
- cut -c1,3,4,5 filename  (prints first, third, fourth, fifth character of each line)
- cut -c1-6  filename(print first 6 characters of each line)
- cut -c2-5,7-9  filename
- cut -d: -f 1 /etc/passwd  (here -d is delimiter which is separator, -f is field It's give first field of the separator as output i.e. usernames)
NOTE: by using cut command we can obtain any field of a CSV file where "," is the delemiter. Ex: cut -d, -f 3 customers-100.csv
### awk
- AWK is a utility designed for data extraction. most of the time it is used to extract fields from a file or output.
- awk '{print $1}' filename   (this will print first column of the lines in the file)
- awk '{print $1,$4}' filename  (first and 4th column)
- awk '/regex/ {print}' filename
- awk -F: '{print $1}' /etc/passwd  (it'll print usernames)
- echo "Hello Tom" | awk '{$2="Subham"; print $0}'    (this will print "Hello Subham")
- awk 'length($0) > 15' filename    (print more then 15 chars lines)