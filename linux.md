### linux command



##  AWK


AWK:- Aho-weinberger-kernighan

## syntax:-

> awk options 'selection_criteria {actions}' Input_file

1. awk: key word we should pass before
2. option: like delimiter what we are passed before in data
3. selection_criteria: we should pass the condition ($3== 'kesava')
4. actions: we should pass the columns like $1,$2... 
5. Input_file: filename

> we will be using below varibles in actions

$0                  - entire line
$1,$2,$3,....       - first,second,third columns
NR                  - Line number in the given inputfile 
NF                  - Number of columns in each line of the given input

## Tables

> emp_s.txt

101 |kesav |developer |Technology |5000

102 |raj |manager |sales |6000

103 |kumar |DBA |Technology |4000

> emp_ns.txt

101|kesav|developer|Technology|5000

102|raj|manager|sales|6000

103|kumar|DBA|Technology|4000

---

## Tilda(~) use

- '~' is equl to 'like'

- if we have any spaces in data then we use the '~' symbole

> Example:-

1. we have emp_s data
2. here ever column or word have some space to we are using here      '~' symbole

101 |kesav |developer |Technology |5000

102 |raj |manager |sales |6000

with out space we are using "==" but here we have spaces so '~' this symbole to check the column like see below

$3 ~ developer

---

- I want to print only 1st to 3rd line how to print that simple see below

> awk -F"|" 'NR==1,NR==3 {print $0}' emp_ns.txt

- Below command use to store data directly in file

> awk -F"|" 'NR==1,NR==3 {print NR,$1,$2,$3,$4}' emp_s.txt

- comparission and display the data

> awk -F"|" '$1 > 101 && $4 ~ "sales" {print NR,$0}' emp_s.txt

> 102 |raj |manager |sales |6000

- use regular expression

> awk -F"|" '$4 ~ /[Ss]ale[Ss]/ {print NR,$0}' emp_s.txt

> 2 102 |raj |manager |sales |6000

- how to do manuplation 

> awk -F"|" '$4 ~ /[Ss]ale[Ss]/ {print NR,$0*2}' emp_s.txt

> 2 204

- how to call external file using awk

- save file as call.awk and call this function using awk. 

> cat > call.awk

> awk -F"|" $1==101 {print NR,$1*2}

- use below one to call external file

> awk -F"|" -f call.awk emp_s.txt

>2 204

- Below one use to change the delimiter

kesava@kesava-PC MINGW64 ~
$ awk -F"|" '$1 == 102 {print $1"-"$2"-"}' emp_s.txt
102 -raj -

kesava@kesava-PC MINGW64 ~
$ awk -F"|" '$1 == 102 {print $1"-"$2"-"$3}' emp_s.txt
102 -raj -manager

kesava@kesava-PC MINGW64 ~
$ awk -F"|" '$1 == 102 {print $1".."$2".."$3}' emp_s.txt
102 ..raj ..manager

- counting operation use awk
## Example1:

>awk -F"|" '$1>100 {count++; print count,$1,$2,$3,$4,$5}' emp_s.txt

1 101  kesav  developer  Technology  5000
2 102  raj  manager  sales  6000
3 103  kumar  DBA  Technology  4000

## Example2:

> awk -F"|" '$4=="Technology" {count++; print count,$1,$2,$3,$4,$5}' emp_ns.txt 

1 101 kesav developer Technology 5000
2 103 kumar DBA Technology 4000

- To display line the columns not more then 5

> awk -F"|" 'NF!=5 {print NF,$0}' emp_s.txt

6 104 |pavan |DBA |Technology |6000 |23/09/2017
---
- use BEGIN and END command in awk

## syntax:

> awk -F"|" 'BEGIN {action} processing statement END {action and result printing}'

## Example1:

> awk -F"|" 'BEGIN {count=0;} {count++} END {print "Total no of lines:",count;}' emp_s.txt

Total no of lines: 4

- without BEGIN statement to write directly

> awk -F"|" '{count++;} END {print "total no of counts",count}' emp_s.txt

total no of counts 4

- without option statement (without delimiter like -F"|")

> awk 'BEGIN {FS="|"; count=0;} {count++;} {print "total no.of counts",count;}' emp_ns.txt

total no.of counts 1
total no.of counts 2
total no.of counts 3

> NOTE: Here FS="|" function we are using here to set delimiter.

## Example2:

> awk -F"|" 'BEGIN {bonus_points=.25;}{bonus = $1*bonus_points; print $0"|"bonus;}' emp_s.txt
101 |kesav |developer |Technology |5000|25.25
102 |raj |manager |sales |6000|25.5
103 |kumar |DBA |Technology |4000|25.75
104 |pavan |DBA |Technology |6000 |23/09/2017|26

## Example3:

>  awk 'BEGIN {count=0;} $4 ~ Technology {count++;} END {print "total no.of peoples",count;}' emp_s.txt

total no.of peoples 4

## Example4:

> awk 'BEGIN {count=0;} $4 ~ Technology {count++;} {print "total no.of peoples",count;}' emp_s.txt

total no.of peoples 1
total no.of peoples 2
total no.of peoples 3
total no.of peoples 4

## Example5:

> awk -F"|" '$4 ~ Technology {count++;tot+=$1; print count,$2,$3,$4} END {print "Average salary:",tot/count}' emp_s.txt
1 kesav  developer  Technology
2 raj  manager  sales
3 kumar  DBA  Technology
4 pavan  DBA  Technology
Average salary: 102.5


total no.of peoples 4

## Builtin functions in awk 

> lenght it return the length of the complete line

> length(x) it's return the length of the 'x' like column

- example:

> awk -F"|" '{print length($4)}' emp_s.txt

11
6
11
11

- To find the index

 - index(s1,s2) returns position of string s2 in s1
 Eg:- x=index("abcdef","b") returns 2
 
> awk -F"|" 'BEGIN {x=index("abcdef","b"); print x}'

 2
 
- To find the substring

 - substr(str,m,n) returns portion of string of length n,string from position m in the given string str.
 Eg: substr("Unix",2,3) return "nix"



- To find out the lines less then 30 character to print it

> awk -F"|" 'length < 30 {print}' emp_ns.txt

102|raj|manager|sales|6000
103|kumar|DBA|Technology|4000

(OR)

> awk -F"|" 'length < 30 {print $0}' emp_ns.txt

 102|raj|manager|sales|6000
 103|kumar|DBA|Technology|4000

> Note: {print} or {print $0} both are same.

- To print the specific column grater then 3 to print it

> awk -F"|" 'length($2) > 3 {print}' emp_ns.txt
 
 101|kesav|developer|Technology|5000
 103|kumar|DBA|Technology|4000

- To print the length of the word 

> echo "welcome" | awk '{print length}'

 7
