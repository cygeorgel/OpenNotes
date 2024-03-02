
Here are some useful Linux commands for handling large CDR files.

###  Simple lines count

Simple lines count:

```
wc -l *
```

To a variable:

```
lines_count=$(wc -l * | tail -n 1 | awk '{print $1}')
```

###  awk

Extracting the unique values of column 8:

```
awk -F ";" '{ a[$8]++ } END { for (b in a) { if (b >= 1) print b } }' file.cdr > extensions.csv
```

Summing column 7:

```
awk -F' ' '{sum+=$7;} END{print sum;}' files*.cdr
```

```
awk -F' ' '{sum+=$7;} END{print sum;}' grnti_202206*
```

Extracting where column 2 is "Nov":

```
 awk '$2 == "Nov"' file.txt
```

Extracting where column 7 is not 0:

```
awk -F ';' '$7 != 0' myfile.cdr
```

Extracting where column 6 is not "incoming":

```
awd -F ';' '$6 != "incoming"' myfile.cdr
```

De-duplicating:

```
awk -F " " ' { if (!visited[$8]++) print }' * > deduplicated_file
```

```
awk '!visited[$0]++' your_file > deduplicated_file
```

https://opensource.com/article/19/10/remove-duplicate-lines-files-awk

###  grep | egrep

```
for i in {01..28}; do echo -n "Feb $i: "; grep ";2023-02-$i;" *.csv | wc -l; done
```

counting the number of rows were position 32 is not 0

```
egrep -v '^.{32}0' grnti_* | wc -l
```

###  mv

When you have files in different subdirectories (for example one per day) and you need to move all of them to the parent directory :

```
mv **/*.csv $(pwd) 
```
