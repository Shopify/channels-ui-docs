---
name: OnboardingInfo
---

# Onboarding info

The onboarding info component contains information that is good to know for merchants before they start onboarding. Things to include in a disclaimer item:

- Transaction fees, mandatory payments, subscription fees, etc.
- Order, shipping, or packaging requirements.
- Strict timelines for fulfilment or delivery (if you have any).
- Anything that might prevent a merchant from succeeding with your platform.

## Props

| Name        | Type    | Description                                                      | Default | Required |
| ----------- | ------- | ---------------------------------------------------------------- | ------- | -------- |
| items       | Item[]  | List of items to render                                          |         | Yes      |
| action      | Action  | Action rendered as a primary button if the step is not completed |         | Yes      |
| description | String  | Content to display above the items                               |         |          |
| completed   | Boolean | Whether the step is completed                                    | false   |          |

### Item

| Name    | Type                    | Description                | Required |
| ------- | ----------------------- | -------------------------- | -------- |
| title   | String                  | Title content for the item | Yes      |
| content | React.Element or String | Item content               | Yes      |
| iconSrc | SVG                     | Source for the item icon   |          |
| iconAlt | String                  | Alt text for the item icon |          |

---

## Best practices

- This component should be wrapped in an <OnboardingCard /> component
- The `action` prop is used to render a primary button if the `completed` prop is false. The merchants should click the button to acknowledge that they understand the items listed above.
- The `description` prop can be used to provide additional context about what is expected from the merchants as part of this onboarding step.
- Each item can include an icon to add clarity or assist in visualizing the meaning.
- The `OnboardingChecklist` component should be used instead if the items are mandatory for a merchant to complete before onboarding.

---

## Examples

### With blurb

```jsx
<OnboardingInfo
  items={[{title: 'Item 1', content: 'Some content'}]}
  description="Some blurb"
  action={{
    onAction: () => {},
    content: 'I understand',
  }}
/>
```

### Without blurb

```jsx
<OnboardingInfo
  items={[{title: 'Item 1', content: 'Some content'}]}
  action={{
    onAction: () => {},
    content: 'I understand',
  }}
/>
```

### Completed

```jsx
<OnboardingInfo
  items={[{title: 'Item 1', content: 'Some content'}]}
  action={{
    onAction: () => {},
    content: 'I understand',
  }}
  completed
/>
```

### With React.ReactNode item content

```jsx
<OnboardingInfo
  items={[{title: 'Item 1', content: <>Some React fragment</>}]}
  description="Some blurb"
  action={{
    onAction: () => {},
    content: 'I understand',
  }}
/>
```

### With string item content

```jsx
<OnboardingInfo
  items={[{title: 'Item 1', content: 'Some content'}]}
  description="Some blurb"
  action={{
    onAction: () => {},
    content: 'I understand',
  }}
/>
```
