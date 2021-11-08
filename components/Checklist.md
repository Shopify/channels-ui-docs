---
name: Checklist
---

# Checklist

A checklist consists of mandatory requirements that merchants must meet to sell on a channel. This component should be rendered on the Settings page, and contain the same items surfaced to merchants during the onboarding flow via the OnboardingChecklist component. The OnboardingChecklist component is actually built using this component.

---

## Props

| Name          | Type    | Description                                                               | Default | Required |
| ------------- | ------- | ------------------------------------------------------------------------- | ------- | -------- |
| items         | Item[]  | List of items for the checklist                                           |         | Yes      |
| loading       | boolean | Replaces each item with a skeleton state                                  |         |          |
| nonCollapsing | boolean | Whether the checklist collapses when all items are completed              | false   |          |
| completeLabel | string  | Content to display in the collapsible button when all items are completed |         |          |

### Item

| Name            | Type                | Description                                               | Required |
| --------------- | ------------------- | --------------------------------------------------------- | -------- |
| label           | string              | The label for the item                                    | Yes      |
| action          | Action              | The action triggered when the uncompleted item is clicked | Yes      |
| completed       | boolean             | Whether the item is completed                             | Yes      |
| completedAction | Action              | The action triggered when the completed item is clicked   |          |
| nested          | ChecklistItemType[] | Items to display in a checklist below the item            |          |

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

- This component should be rendered on the Settings page, contained in a Polaris <Card /> component. To add a checklist to the onboarding page, please use the <OnboardingChecklist /> component.
- When rendered on the Settings page, the `completeLabel` prop should be provided and the `nonCollapsing` prop should be false, which is the default value.
- The items provided to this component on the Settings page should match those provided to the <OnboardingChecklist /> component in the onboarding flow.
- Automatically check and confirm as many of the requirements as possible.
- Define every requirement with a clear action that the merchant needs to take.
- Incomplete items will render as links, which can point to a Shopify Admin section, help docs or open a modal with additional information on how to fulfill the requirement.
  - Completed items can also act as links based on an optional `completedAction` prop.
- Items can have one level of nested items if there are substeps required to fully complete the item.
  - The nested items will only be actionable once the parent item has been set as completed.
  - The parent item will be shown as completed when all nested items have been marked as completed.

---

## Examples

### Loading

```jsx
<Checklist
  loading
  items={[
    {
      label: "First Item",
      action: {},
      completed: true,
    },
    {
      label: "Second Item",
      action: {},
      completed: false,
    },
    {
      label: "Third Item",
      action: {},
      completed: true,
    },
  ]}
/>
```

### Completed

```jsx
<Checklist
  completeLabel="Your shop meets the requirements"
  items={[
    {
      label: "First Item",
      action: {},
      completed: true,
    },
    {
      label: "Second Item",
      action: {},
      completed: true,
    },
    {
      label: "Third Item",
      action: {},
      completed: true,
    },
  ]}
/>
```

### Non-Collapsing

```jsx
<Checklist
  nonCollapsing
  items={[
    {
      label: "First Item",
      action: {},
      completed: true,
    },
    {
      label: "Second Item",
      action: {},
      completed: true,
    },
    {
      label: "Third Item",
      action: {},
      completed: true,
    },
  ]}
/>
```

### Completed Item Actions

```jsx
<Checklist
  items={[
    {
      label: "First Item",
      action: {},
      completed: true,
      completedAction: {},
    },
    {
      label: "Second Item",
      action: {},
      completed: false,
    },
    {
      label: "Third Item",
      action: {},
      completed: true,
    },
  ]}
/>
```

### Nested

```jsx
<Checklist
  items={[
    {
      label: "First Item",
      action: {},
      completed: true,
    },
    {
      label: "Second Item",
      action: {},
      completed: true,
      nested: [
        {
          label: "Nested Item",
          action: {},
          completed: false,
        },
      ],
    },
    {
      label: "Third Item",
      action: {},
      completed: true,
    },
  ]}
/>
```
