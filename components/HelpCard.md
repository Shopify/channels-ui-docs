---
name: HelpCard
---

# Help card

Help cards are used on the help page to provide a consistent wrapper around each help section.

---

## Props

| Prop name | Type       | Optional |
| --------- | ---------- | -------- |
| id        | string     | false    |
| title     | string     | false    |
| children  | ReactNode  | false    |
| icon      | IconSource | true     |
| startOpen | IconSource | true     |

---

## Best practices

- Each card should contain a set of related help content and links
- The title should be descriptive of what help content is contained in the card
- The children can contain text, links, or embedded videos. Help content should be rendered in the context of the channel using an embedded modal where possible.
- The startOpen prop can be used to have a specific help card open when the page loads.

---

## Examples

### Basic help card

```jsx
<HelpCard id="collapsible-card-1" title="Getting started">
  Help content about getting started with the channel
</HelpCard>
```

### Help card with an icon

```jsx
<HelpCard id="collapsible-card-1" title="Getting started" icon={PlayMinor}>
  Help content about getting started with the channel
</HelpCard>
```

### Help card that starts open

```jsx
<HelpCard id="collapsible-card-1" title="Getting started" startOpen>
  Help content about getting started with the channel
</HelpCard>
```
