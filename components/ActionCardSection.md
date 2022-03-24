---
name: ActionCardSection
---

# Action card section

This component is meant to provide an easy way to embed simple, single action steps into your onboarding flow. It can also be used on the settings page to surface simple actions the merchant can take after onboarding.

---

## Props

| Name     | Type          | Description                                 | Default | Required |
| -------- | ------------- | ------------------------------------------- | ------- | -------- |
| children | ReactNode     | Main content to display in the card section |         | Yes      |
| action   | ComplexAction | Call to action                              |         |          |

### ComplexAction

| Name               | Type       | Description                                                  |
| ------------------ | ---------- | ------------------------------------------------------------ |
| id                 | string     | A unique identifier for the action                           |
| content            | string     | Content the action displays                                  |
| accessibilityLabel | string     | Visually hidden text for screen readers                      |
| url                | string     | A destination to link to                                     |
| external           | boolean    | Forces url to open in a new tab                              |
| onAction           | () => void | Callback when an action takes place                          |
| onMouseEnter       | () => void | Callback when mouse enter                                    |
| onTouchStart       | () => void | Callback when element is touched                             |
| disabled           | boolean    | Whether the action is disabled                               |
| destructive        | boolean    | Whether the action is destructive                            |
| icon               | IconSource | Source of the icon                                           |
| outline            | boolean    | Whether the action should be displayed as an outlined button |
| loading            | boolean    | Whether a spinner should be displayed                        |

IconSource = React.SFC<React.SVGProps<SVGSVGElement>> | 'placeholder' | string;

---

## Best practices

- This component should be rendered inside an `OnboardingCard` if used on the onboarding page, or a `Card` component if used on the settings page.
- The `action` prop is used to render a button that the merchant can click
  to take action on the specific onboarding step.
  - If it is a one-time action, the `action` prop should no longer be provided once the merchant has actioned on it.
  - If it is a persistent action (i.e. a toggle to enable/disable something) then the `action` prop should between a primary and non-primary action.

---

## Examples

### Basic action card section

```jsx
<ActionCardSection
  action={{
    content: 'I accept',
    primary: true,
  }}
>
  <p>
    In order to complete setup, you must read and accept Mockingbird’s{' '}
    <Link>Terms of Service.</Link>
  </p>
</ActionCardSection>
```

### Action card section without an action

```jsx
<ActionCardSection>
  <p>
    You have accepted the Mockingbird <Link>Terms of Service.</Link>
  </p>
</ActionCardSection>
```

### Action card section in an onboarding card

```jsx
<OnboardingCard
  id="mockingbird-checkout"
  state="active"
  title="Mockingbird checkout"
>
  <ActionCardSection
    action={{
      content: 'Enable',
      primary: true,
    }}
  >
    <p>
      Enable onsite checkout to allow customers to purchase your products
      directly on Mockingbird's surfaces.
    </p>
  </ActionCardSection>
</OnboardingCard>
```

### Action card section in a card

```jsx
<Card title="Mockingbird Checkout">
  <ActionCardSection
    action={{
      content: 'Disable',
    }}
  >
    <p>
      Disable onsite checkout. Customers will be redirected from Mockingbird's
      surfaces to your online store to complete checkout.
    </p>
  </ActionCardSection>
</Card>
```
