---
name: HelpPage
---

# Help page

Used to build the outer wrapper of the help page, including the page title, content, and footer.

---

## Props

| Prop name | Type      | Optional |
| --------- | --------- | -------- |
| title     | string    | false    |
| children  | ReactNode | false    |
| footer    | ReactNode | true     |

---

## Best practices

The help page component should:

- Always provide a title for the page header
- Children should consist of 1 or more Help Card components
- Use the footer to direct merchants to help documentation related to the channel

---

## Examples

### Basic help page

```jsx
<HelpPage title="Frequently asked questions">Help content</HelpPage>
```

### Help page with footer

```jsx
<HelpPage title="Frequently asked questions" footer="What is Mockingbird?">
  Help content
</HelpPage>
```
