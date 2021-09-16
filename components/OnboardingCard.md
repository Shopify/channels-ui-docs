---
name: OnboardingCard
---

# Onboarding card

Onboarding cards are used on the onboarding page to provide a consistent wrapper around each step.

---

## Props

| Name      | Type      | Description                                                      | Required |
| --------- | --------- | ---------------------------------------------------------------- | -------- |
| id        | string    | A unique identifier for the card                                 | Yes      |
| title     | string    | Title content for the card                                       | Yes      |
| children  | ReactNode | Inner content of the card                                        | Yes      |
| state     | State     | Sets the state of the card                                       | Yes      |
| footer    | string    | Content to render in a subdued section at the bottom of the card |          |
| sectioned | string    | Auto wrap content in section                                     |          |
| action    | Action    | Card header action, rendered as a basic button                   |          |

State = 'active' | 'completed' | 'disabled';

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

- The merchant's current onboarding step should use a onboarding card with the `active` state. There should be at most one card in the active state.
- Onboarding steps that have been completed should use onboarding cards with the `completed` state.
- Upcoming onboarding steps should use onboarding cards with the `disabled` state, so merchants can focus on completing their current
- The component should be rendered with the `sectioned` prop set to true or with children that are wrapped in a `Card.Section`
  - Onboarding components such as `OnboardingIntro`, `OnboardingInfo`, `OnboardingChecklist`, and `AccountConnection` wrap their children in a `Card.Section` and should not be wrapped again

---

## Examples

### Active onboarding card

```jsx
<OnboardingCard
  id="onboarding-card-1"
  title="Introduction to ads onboarding"
  state="active"
>
  <Card.Section>Introduction card contents</Card.Section>
</OnboardingCard>
```

### Completed onboarding card

```jsx
<OnboardingCard
  id="onboarding-card-1"
  title="Introduction to ads onboarding"
  state="completed"
>
  <Card.Section>Introduction card contents</Card.Section>
</OnboardingCard>
```

### Disabled onboarding card

```jsx
<OnboardingCard
  id="onboarding-card-1"
  title="Introduction to ads onboarding"
  state="disabled"
>
  <Card.Section>Introduction card contents</Card.Section>
</OnboardingCard>
```

### Sectioned onboarding card

```jsx
<OnboardingCard
  sectioned
  id="onboarding-card-1"
  title="Introduction to ads onboarding"
  state="active"
>
  Introduction card contents
</OnboardingCard>
```

### Onboarding card with a footer

```jsx
<OnboardingCard
  id="onboarding-card-1"
  title="Introduction to ads onboarding"
  state="active"
  footer="Introduction card footer content"
>
  <Card.Section>Introduction card contents</Card.Section>
</OnboardingCard>
```

### Onboarding card with an action

```jsx
<OnboardingCard
  id="onboarding-card-1"
  title="Introduction to ads onboarding"
  state="active"
  action={{
    content: 'Learn more',
  }}
>
  <Card.Section>Introduction card contents</Card.Section>
</OnboardingCard>
```
