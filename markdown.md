### markdown learning

# sections

- [Headers](#headers)
- [Quotes](#quotes)
- [Emphasis](#emphasis)
- [Horizontal Rule](#horizntal-rule)
- [Lists](#lists)
- [links](#links)
- [Images](#images)
- [code](#code)
- [Tables](#tables)
- [custom HTML](#custom-html)
- [custom css](#custom-css)
- [Additional Resources](#additional-resources)

## if u want horizantal line use this (---)
---

## Headers

headers are defined by the '#' symbol. one '#' for h1 '##' for h2 and etc.

<!--
    Example

    # H1 Header
-->


> **TODO** create an H1 
 
# Header 1

> **TODO** create an H2

## Header 2

> **TODO** create an H3

### Header 3

> **TODO** create an H4 

#### Header 4

---

## Quotes

quotes are defined by the '>' symbol

<!--
Example

> This is an example quote

-->


>**TODO**. create a quote

>this is my quote

you can combine a heder with a quote

<!--

> # H1 Quote

-->

> # H1 Quote

---

## Emphasis

use to do bold and italic
it is for bold (**Bold**), it is for italic (*italic*) and it is also italic(_italic_)

> **BOLD** letters

> *italic* letters

> _italic_ letters

---

## Horizontal Rule

<!--

Example

---
***
___

-->

use hypens,asterisks and underscores(-,*,_).

> hypens(---)

> asterisks(***)

> underscore(___)

> **See Below** create a horizontal rule

---
***
___

> Note:-we use anything in this 3 all are same.

## Lists

> use (-,*,+) and space to create UnOrder list

- list
    - sublist
        - another sublist

* list

+ list
  
> Order list

1. Item 1
2. Item 2
3. Item 3
1. Item 4 (by mistakly u give any number it take orderly you don't worry)

***

## Links

> use angler brackets('<>') to create a links

<https://www.google.com>

[click me to go directly google](https://www.google.com)

> other links

<!--

[1] : https://www.google.com

-->
[website]: http://www.google.com

<!--

[my website][1]
-->

[click][website]

[code](#code) when i click this it go to the code section


> To set images aslo for links


![image](C:\Users\kesava\Desktop\1.jpg)


[profile]:
https://www.pexels.com/photo/white-and-yellow-flower-with-green-stems-36764/

![image][profile]

---

## code

> To heligth the code then you use this dots (starting ```
>and ```)

```HTML
<div>
    <p> This is Paragraph</p>
</div>  

```

``` javascript
var a = 10 ;
a = a + 1 ;
```

---

## Tables

how to create table see below

<!--
| Header1 | Header2 | Header3 |
| --- | --- | --- |
| col1 | col2 | col3 |

[OR]

| Header1 | Header2 | Header3 |
|-------- | ------- | ------- |
| col1    | col2    | col3    |

-->

| Header1 | Header2 | Header3 |
|---|---|---|
|   col1  |    col2 |    col3 |

> To Arrange this into other way

| Header1 | Header2 | Header3 |
|---------| :-----: | ------:|
|Aligned left | Aligned center | Aligned Right |

---

## custom HTML

Since MarkDown gets Automatically converted to HTML, you can add row HTML directly to your MarkDown.

```html
<p>sample HTML Div</p>
```
> Header creation using normal html
 
<h1> Header 1 </h1> 

> Header creation using MarkDown

# Header 1 

---

## custom CSS

``` html
    <style>
        body{
             color:red;   
        }
    </style>    
```

> if you want to use css it is also possible

<style>
    p{
        color:red
    }
</style>

---