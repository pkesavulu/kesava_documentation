# Angularjs 2:-
---

--> To run this program use this ng serve --open.
--> when we run this application it will compile and rendering the app.

## ways for accessing the properties from component to template:-
---

### 1)property binder
---
> Our result is boolean,number,text any thing we go for property binder.

<tag [attr]> = "propertyname"/>

#### Ex:-
---

1.component.html
<div>
<button [disable]="btndisable">click me</button>
<div>
2.component.ts
export class AppComponent{
	btndisabled : boolean = true;
}

### 2)interpolation:-
---
> Given result is plain text then simply you go for interpolation other wise go for property binder.

{{}}

#### Ex:-
---

{{SampleText}}


## NG Directive
---

### *ngFor:-
--- 

> It is use to repeat the given value like same as "foreach" in java.

ex1:-
---

```
<tr *ngFor="let x in [array/data/collection]">
</tr>
```

ex2:-
---

if you want index number for your table just use 'index' like this.

```

<tr *ngFor="let x in [array/data/collection]; let i in index">
</tr>

```

### *ngIf:-
---

* ->(structural directive) It is use to create the element or destroy the element.

<tag *ngIf='expression'>

expression - result either true or false

if we use ngIf it condition fails it remove dom object completly that is the advantage of the ngIf.





