---
Programming Language: JavaScript
Framework/Library: ReactJS
Type: fundamentals
Topic: Props
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Working with Components, Props, and JSX
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - ReactJS
  - javascript
  - props
---
---

> [!abstract] Props
> - Short for __Property__
> - __How we pass data between components.__
> - Are used to pass data from __parent components__ to ___child components___ (down the component tree)
> - Essential tool to __configure__ and *customize* components (like function parameters)
> - With props, parent components **control** how child components look and work
> - **Anything** can be passed as props:
> 	- single values
> 	- `arrays`
> 	- `objects`
> 	- `functions`
> 	- even other `components`

---

```js
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
- This basically becomes a template

```js
function Menu() {
  return (
    <main className="menu">
      <h2>Our Menu</h2>
      <Pizza
        name="Pizza Spinaci"
        ingredients="Tomato, mozarella, spinach, and ricotta cheese"
        photoName="pizzas/spinaci.jpg"
        price={12}
      />

      <Pizza
        name="Pizza Funghi"
        ingredients="Tomato, mozarella, mushrooms, and onion"
        price={12 * 3} // example math operation
        photoName="pizzas/funghi.jpg"
      />
    </main>
  );
}
```
- `price={12}` is enclosed with a _bracket `{ }`_ because it's __supposed to be an Integer__, so we can do math operations to it
  > __If a Prop value is not a `string`, enclose it with Curly Braces__

