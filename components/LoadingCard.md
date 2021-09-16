---
name: LoadingCard
---

# LoadingCard

Helper to deploy loading states for cards within layouts.

---

## Props

| Name    | Type    | Description                                          | Default |
| ------- | ------- | ---------------------------------------------------- | ------- |
| wrapped | boolean | Whether the loading states are wrapped in a card     |         |
| basic   | boolean | Uses a spinner if true and skeleton content if false |         |
| lines   | number  | Number of lines to render in the skeleton body text  | 1       |

---

## Examples

### Standard

```jsx
<LoadingCard />
```

### wrapped

```jsx
<LoadingCard wrapped />
```

### basic

```jsx
<LoadingCard basic />
```

### basic + wrapped

```jsx
<LoadingCard basic wrapped />
```

### Multi-line

```jsx
<LoadingCard lines={3} wrapped />
```
