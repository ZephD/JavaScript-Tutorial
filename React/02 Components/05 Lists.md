# Lists

Sometimes we want to render Components based on an array of input data.

For this, we can use the `{}` for JS expressions, and `.map()` over the data.

* The `.map()` function must return a React Node (inc. `null`).
* Each returned item must be given a unique `key` prop.

```javascript
const List = ({ items }) => (
  <ul>
    {items.map(item => (
      <li key={item}>
        {item}
      </li>
    ))}
  </ul>
)

const Page = () => (
  <List items={['Apple', 'Banana', 'Cherry']}/>
)
```

> **Best Practice**
>
> Keys are used by react to track items for rendering optimisation.  
> Therefore, they should be **unique** and **deterministic** (created **from your data**).
> 
> It is bad form to use the array index as the key.