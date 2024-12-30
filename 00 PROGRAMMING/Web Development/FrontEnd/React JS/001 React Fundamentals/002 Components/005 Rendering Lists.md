---
Programming Language: JavaScript
Framework/Library: ReactJS
Type: fundamentals
Topic: Rendering List of Data into Components
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Working with Components, Props, and JSX
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - ReactJS
  - javascript
  - components
---
---
Instead of manually typing data:
```js
<Pizza
	name="Pizza Spinaci"
	ingredients="Tomato, mozarella, spinach, and ricotta cheese"
	photoName="pizzas/spinaci.jpg"
	price={12}
/>

<Pizza
	name="Pizza Funghi"
	ingredients="Tomato, mozarella, mushrooms, and onion"
	price={12}
	photoName="pizzas/funghi.jpg"
/> 
```

(___Not Correct Tho___) This is how to render data from an `array` of `object`:
```js
function Menu() {
  return (
    <main className="menu">
      <h2>Our Menu</h2>

      <div>
        {pizzaData.map((pizza) => (
          <Pizza name={pizza.name} />
        ))}
      </div>
      
      {/* <Pizza
        name="Pizza Spinaci"
        ingredients="Tomato, mozarella, spinach, and ricotta cheese"
        photoName="pizzas/spinaci.jpg"
        price={12}
      />

      <Pizza
        name="Pizza Funghi"
        ingredients="Tomato, mozarella, mushrooms, and onion"
        price={12}
        photoName="pizzas/funghi.jpg"
      /> */}
    </main>
  );
}

function Pizza(props) {
  return (
    <div>
      <img src={props.photoName} alt={props.name} />
      <h3>{props.name}</h3>
      <p>{props.ingredients}</p>
    </div>
  );
}
```
- ___BUT THIS IS STILL NOT THE RIGHT WAY!!!___

> [!done] Correct Way:
```js
function Menu() {
  return (
    <main className="menu">
      <h2>Our Menu</h2>

      <ul className="pizzas">
        {pizzaData.map((pizza) => (
          <Pizza pizzaObj={pizza} key={pizza.name} />
        ))}
      </ul>

    </main>
  );
}

function Pizza(props) {
  return (
    <li className="pizza">
      <img src={props.pizzaObj.photoName} alt={props.pizzaObj.name} />
      <div>
        <h3>{props.pizzaObj.name}</h3>
        <p>{props.pizzaObj.ingredients}</p>
        <span>{props.pizzaObj.price + 3}</span>
      </div>
    </li>
  );
}
```

> [!danger] Error:
> without a unique `key` property we'll get this error:
> ![[Pasted image 20241230003932.png]]
