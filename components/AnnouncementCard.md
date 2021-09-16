---
name: AnnouncementCard
---

# Announcement card

Announcement cards are optional and recommended for when you want to deliver a valuable message to merchants using your channel.

---

## Props

| Name         | Type       | Description                                                                             | Required |
| ------------ | ---------- | --------------------------------------------------------------------------------------- | -------- |
| title        | string     | Title of the card                                                                       | Yes      |
| illustration | string     | URL of the card's illustration                                                          | Yes      |
| children     | ReactNode  | Content to display inside the card                                                      | Yes      |
| onDismiss    | () => void | Callback when the card is dismissed. If not provided, the dimiss button is not rendered |          |
| action       | Action     | Action for the card, rendered as a primary button                                       |          |

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

## When to use this component

- Announcing a new feature
- Recruiting for a beta testing opportunity
- Planned disruption to the channel
- Include an action when there’s an action a merchant can/should take

## Best practices

- Don’t use this component for general education or tips.
- Don’t use for merchant account errors, go for top level banners instead.
- Deliver 1 message, avoid multiple messages and carousels.
- Time cap the component, don’t leave it up indefinitely.

### Flexibility:

- The importance of the message should help you decide if this card is dismissible or not.
- This component is optional and can be skipped when there are no relevant messages.

---

## Examples

### Basic announcement card

```jsx
<AnnouncementCard
  title="Introducing Mockingbird tagging"
  illustration="https://burst.shopifycdn.com/photos/happy-phone.jpg?width=373"
>
  You can now use the Mockingbird channel to set up your products for Instagram
  tagging. Once your products are synced, you’ll be able to tag them in your
  posts and reach more potential customers
</AnnouncementCard>
```

### Announcement card with action

```jsx
<AnnouncementCard
  title="Introducing Mockingbird tagging"
  illustration="https://burst.shopifycdn.com/photos/happy-phone.jpg?width=373"
  action={{
    content: 'Get started',
  }}
>
  You can now use the Mockingbird channel to set up your products for Instagram
  tagging. Once your products are synced, you’ll be able to tag them in your
  posts and reach more potential customers
</AnnouncementCard>
```

### Dismissible announcment card

```jsx
<AnnouncementCard
  title="Introducing Mockingbird tagging"
  illustration="https://burst.shopifycdn.com/photos/happy-phone.jpg?width=373"
  onDismiss={() => {}}
>
  You can now use the Mockingbird channel to set up your products for Instagram
  tagging. Once your products are synced, you’ll be able to tag them in your
  posts and reach more potential customers
</AnnouncementCard>
```

### Announcment card with all elements

```jsx
<AnnouncementCard
  title="Introducing Mockingbird tagging"
  illustration="https://burst.shopifycdn.com/photos/happy-phone.jpg?width=373"
  onDismiss={() => {}}
  action={{
    content: 'Get started',
  }}
>
  You can now use the Mockingbird channel to set up your products for Instagram
  tagging. Once your products are synced, you’ll be able to tag them in your
  posts and reach more potential customers
</AnnouncementCard>
```

## Accessibility

The required `title` prop gives the callout card a level 2 heading (<h2>). This helps with readability and provides structure to screen reader users.

The illustrations included in announcement card is implemented as a decorative image with an empty alt attribute (alt="" ), and will be skipped by screen readers.
