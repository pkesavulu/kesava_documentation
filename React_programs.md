React:-
---

Example:1
---

let cart = 0;
cart = 5;
//function for checking car is empty or not

function getCart(){
if(cart){ //checking cart is not empty? then return full
return "cart is full"
}
else return "cart is empty" //cart is empty then return this
}


class Cart extends React.Component{

render(){

return (<div>
<h1>Cart is :{getCart()}</h1>
</div>)
}

}

ReactDOM.render(
<Cart />,document.getElementById("root")
); 


Example:2
---

let login = true;
let username = "kesava";
class Login extends React.Component{
  render(){
    return(
      <div>
        { 
          login && <h1> welcome {username} </h1>
        } 
        {
          !login && <button>click</button>
        }
    </div>
    )
  }  
}
ReactDOM.render(
<Login/>,document.getElementById("root")
);

Example:3
---


notes:-
---
1. jsx -> xml like syntax
2. before rendering we should transform from jsx to javascript 
3. flux and Redux used for dataflow
4. Loaders & transpilers to convert es6 to es5(bable,typescript)
5. angular 2 is frame work but react just library































