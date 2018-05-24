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
 
