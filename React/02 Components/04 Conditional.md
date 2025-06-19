# Conditional Rendering

Sometimes we want to render a component based on a condition.

Only render the paragraph tag if the message exists.

```javascript
const Message = ({ message }) => (
  <div>
    {message && <p>{message}</p>}
  </div>
)
```

Show a different message depending on the user's state.

```javascript
const User = ({ isLoggedIn }) => (
  <div>
    {isLoggedIn
      ? <p>Welcome back!</p>
      : <p>Please log in</p>
    }
  </div>
)
```