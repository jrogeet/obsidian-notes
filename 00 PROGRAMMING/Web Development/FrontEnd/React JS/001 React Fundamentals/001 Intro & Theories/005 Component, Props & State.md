---
Programming Language: JavaScript
Framework/Library: ReactJS
Type: fundamentals
Topic: Props, Immutability, and One-Way Data Flow
Course: "The Ultimate React Course 2024: React, Next.js, Redux & More"
Section: Working with Components, Props, and JSX
Reference/Resources: https://www.udemy.com/course/the-ultimate-react-course/
tags:
  - programming
  - ReactJS
  - javascript
  - props
  - state
  - components
---
---

## Props and Immutability

![[Pasted image 20241229012956.png]]

> [!tip] Props vs State
> - __`Props`__ are read-only, they are __IMMUTABLE__! 
> 	- This is one of React's strict rules.
> - If you need to mutate props, you actually ***need `State`***
> 
>> [!question] Why?
>> - Mutating `props`/objects would affect parent, creating __side effects__ (not pure)
>>
>>> [!info] Side-Effect
>>> - happens whenever you ___change some data___ that's located **outside of the current function**
>>
>> - `Components` have to be __pure functions__ in terms of `props` and `state`
>> 	- This allows React to optimize apps, avoid bugs, make apps predicatble

---
## One-Way Data Flow
- In React applications, data can only be passed from __parent__ to ___child components___
	- Top to Bottom, Never Bottom to Top
	- ![[Pasted image 20241229015512.png]]
- ... makes applications more predictable and easier to understand
- ... makes applications easier to debug, as we have more control over the data
- ... is more performant

> _Angular_ has two-way data flow

