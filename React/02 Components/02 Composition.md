# Composition

A component can use other components.

```javascript
const Title = () => <h1>Hello World</h1>
const Paragraph = () => <p>Welcome to my page</p>

const Page = () => (
  <div>
    <Title/>
    <Paragraph/>
  </div>
)

export default Page
```

A component is said to have "child" components, when nested like this.

## [React Fragment](https://react.dev/reference/react/Fragment)

Components must return only one React Node.

Often, this means wrapping a bunch of Components in a (a simple) `<div>` element,
which adds an unnecessary DOM element.

React has a special element for this purpose, the "empty" element, known as a React Fragment.

```javascript
const FragmentTest = () => (
  <>
    <p>One</p>
    {1 + 1}
    Three
  </>
)
```