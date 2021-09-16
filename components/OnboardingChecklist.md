---
name: OnboardingChecklist
---

# Onboarding checklist

An onboarding checklist consists of things that are mandatory for the merchant to complete prior to onboarding. This component should be rendered in a Collapsible Card on the onboarding page, and marked as completed when all items are marked as completed.

---

## Props

| Name  | Type                      | Description                               | Required |
| ----- | ------------------------- | ----------------------------------------- | -------- |
| items | OnboardingChecklistItem[] | List of items to display in the checklist | Yes      |

### OnboardingChecklistItem

| Name            | Type            | Description                              | Required |
| --------------- | --------------- | ---------------------------------------- | -------- |
| label           | string          | Text content of the item                 | Yes      |
| action          | Action          | Action for the item                      | Yes      |
| completed       | boolean         | Whether the item is completed            | Yes      |
| completedAction | Action          | Action for the item when it is completed |          |
| nested          | ChecklistItem[] | List of nested items                     |          |

#### ChecklistItem

| Name            | Type    | Description                              | Required |
| --------------- | ------- | ---------------------------------------- | -------- |
| label           | string  | Text content of the item                 | Yes      |
| action          | Action  | Action for the item                      | Yes      |
| completed       | boolean | Whether the item is completed            | Yes      |
| completedAction | Action  | Action for the item when it is completed |          |

---

## Best practices

- This component should be wrapped in an <OnboardingCard /> component
- Automatically check and confirm as many of the requirements as possible.
- Define every requirement with a clear action that the merchant needs to take.
- Incomplete items will render as links, which can point to a Shopify Admin section, help docs or open a modal with additional information on how to fulfill the requirement.
  - Completed items can also act as links based on an optional `completedAction` prop.
- Items can have one level of nested items if there are substeps required to fully complete the item.
  - The nested items will only be actionable once the parent item has been set as completed.
  - The parent item will be shown as completed when all nested items have been marked as completed.

---

## Examples

### Basic onboarding checklist

```jsx
<OnboardingChecklist
  items={[
    {
      label: 'Item 1',
      action: {
        onAction: () => {},
      },
      completed: true,
    },
    {
      label: 'Item 2',
      action: {
        onAction: () => {},
      },
      completed: false,
    },
  ]}
/>
```

### Onboarding checklist with nested items

```jsx
<OnboardingChecklist
  items={[
    {
      label: 'Item 1',
      action: {
        onAction: () => {},
      },
      completed: true,
    },
    {
      label: 'Item 2',
      action: {
        onAction: () => {},
      },
      completed: false,
      nested: [
        {
          label: 'Nested item',
          completed: false,
          action: {
            onAction: () => {},
          },
        },
      ],
    },
  ]}
/>
```

### Onboarding checklist with completed items that are actionable

```jsx
<OnboardingChecklist
  items={[
    {
      label: 'Item 1',
      action: {
        onAction: () => {},
      },
      completedAction: {
        onAction: () => {},
      },
      completed: true,
    },
    {
      label: 'Item 2',
      action: {
        onAction: () => {},
      },
      completed: false,
    },
  ]}
/>
```
