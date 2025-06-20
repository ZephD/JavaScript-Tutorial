# Never Nester

Sometimes, code can get quite nested/deep,
with many code blocks inside code blocks.

```javascript
const processOrders = orders => {
  for (let i = 0; i < orders.length; i++) {
    const order = orders[i]
    if (order.active) {
      for (let j = 0; j < order.items.length; j++) {
        const item = order.items[j]
        if (item.stock > 0) {
          if (!item.discontinued) {
            // processing logic here
          }
        }
      }
    }
  }
}
```

This makes code hard to read/follow, and you often have to keep a lot of state in your mind.

There are tricks you can employ to reduce this nesting.

## Extraction

Extract snippets of code into functions.

```javascript
const processItems = items => {
  for (let j = 0; j < items.length; j++) {
    const item = items[j]
    if (item.stock > 0) {
      if (!item.discontinued) {
        // processing logic here
      }
    }
  }
}

const processOrders = orders => {
  for (let i = 0; i < orders.length; i++) {
    const order = orders[i]
    if (order.active) {
      processItems(orders.items)
    }
  }
}
```

## Inversion

Instead of handling the "happy path" of a `if` statement first,
invert it to handle the other path first.  
Then you can return early (often on a single line) and remove the need for an else code block.

```javascript
const processItems = items => {
  for (let j = 0; j < items.length; j++) {
    const item = items[j]
    if (item.stock <= 0) continue // Skip Item
    if (item.discontinued) continue // Skip Item
    // Process Logic Here
  }
}

const processOrders = orders => {
  for (let i = 0; i < orders.length; i++) {
    const order = orders[i]
    if (!order.active) continue // Skip order
    processItems(order.items)
  }
}
```

This creates a sort of "validation" layer, before running the actual code logic.