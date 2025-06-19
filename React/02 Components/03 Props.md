# Props

Functions have inputs, and Components are no different.

You pass data to Components via the `props` argument.

```javascript
const Greet = (props) => <h1>Hello {props.name}</h1>

const GreetPage = () => (
  <div>
    <Greet name={'Tom'}/>
    <Greet name="Lewis"/>
  </div>
)

export default GreetPage
```

Since `props` is just an object, it can be destructured to retrieve props immediately.

```javascript
const Greet = ({ name }) => <h1>Hello {name}</h1>
```

## Children

`props` has a special property called `children`, which is all the child components.

```javascript
const Card = ({ children }) => (
  <div className="card">
    {children}
  </div>
)

const Page = () => (
  <Card>
    <h1>Title inside Card</h1>
    <p>Paragraph inside Card</p>
  </Card>
)
```