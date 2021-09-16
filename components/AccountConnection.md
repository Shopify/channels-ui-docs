---
name: AccountConnection
---

# Account connection

Use this component to connect the merchant’s account on your platform to Shopify. If they don’t have an account already, suggest creating one. Use the bottom description text to explain why they need an account on your platform or add any relevant info.

This component must be rendered inside a Card or Onboarding Card component.

---

## Props

| Name      | Type    | Description                     | Default | Required |
| --------- | ------- | ------------------------------- | ------- | -------- |
| content   | string  | Content to display as the title |         | Yes      |
| action    | Action  | Action for account connection   |         | Yes      |
| connected | boolean | Set if the account is connected | false   |          |
| avatarUrl | string  | URL for the user's avatar image |         |          |

### Action

| Name               | Type       | Description                             |
| ------------------ | ---------- | --------------------------------------- |
| id                 | string     | A unique identifier for the action      |
| content            | string     | Content the action displays             |
| accessibilityLabel | string     | Visually hidden text for screen readers |
| url                | string     | A destination to link to                |
| external           | boolean    | Forces url to open in a new tab         |
| onAction           | () => void | Callback when an action takes place     |
| onMouseEnter       | () => void | Callback when mouse enter               |
| onTouchStart       | () => void | Callback when element is touched        |

---

## Best practices

- Render within an Onboarding Card if being used on the onboarding page
- Render within a Card if being used on the settings page
- The primary action should open a popup browser window where the merchant can log into your platform
- The Onboarding Card footer can be used to link the merchants out to create an account on your platform

---

## Examples

### Basic account connection

```jsx
<AccountConnection
  content="No account connected"
  action={{
    content: 'Connect account',
  }}
/>
```

### Connected account connection

```jsx
<AccountConnection
  content="test@mockingbird.com"
  action={{
    content: 'Change',
  }}
  connected
/>
```

### Account connection with custom avatar

```jsx
<AccountConnection
  content="test@mockingbird.com"
  action={{
    content: 'Change',
  }}
  connected
  avatarUrl="https://burst.shopifycdn.com/photos/fashion-model-in-fur.jpg?width=373"
/>
```
