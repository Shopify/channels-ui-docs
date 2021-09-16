---
name: FeatureListCard
---

# Feature list card

Feature list card is an overview of all the features that the merchant has onboarded to or started to onboard. It’s an easily digestible list of features with relevant statuses, descriptions, and actions available to merchants.

---

## Props

| Name     | Type          | Description                             | Required |
| -------- | ------------- | --------------------------------------- | -------- |
| features | FeatureItem[] | List of features to display in the card | Yes      |

### FeatureItem

| Name        | Type              | Description                                                                 | Required |
| ----------- | ----------------- | --------------------------------------------------------------------------- | -------- |
| title       | string            | Heading content of the feature                                              | Yes      |
| description | string            | Body content of the feature                                                 | Yes      |
| badge       | FeatureBadgeProps | Badge details for the feature                                               | Yes      |
| progress    | number            | Current onboarding progression of the feature (0-100)                       |          |
| action      | Action            | Call to action for the feature, rendered as a basic button                  |          |
| helpText    | string            | Additional information about the feature, rendered if no action is provided |          |

### FeatureBadgeProps

| Name     | Type   | Description                                     | Required |
| -------- | ------ | ----------------------------------------------- | -------- |
| children | string | Content to display inside the badge             | Yes      |
| status   | Status | Set the color of the badge for the given status |          |

Status = 'success' | 'info' | 'attention' | 'critical' | 'warning' | 'new'

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

- Use table format to display features with onboarding either in progress or completed.
- Provide descriptions below the titles to remind merchants what the features are.
- List features in order of priority:
  1. Features with incomplete onboarding.
  2. Features that need attention or have errors.
  3. Features that have a next step or action (such as Create campaign, View campaign, View analytics etc.).
  4. Features that have no additional actions.
- Use badges to allow quick at-a-glance status of each feature (eg: setup in progress, ready, pending, etc).
- Use the space on the right for CTAs or if no action, additional info.
- For features with incomplete onboarding, use a progress bar with an approximate estimation of setup progress.

---

## Examples

### Basic feature item

```jsx
<FeatureListCard
  features={[
    {
      title: 'Mockingbird Marketplace',
      description:
        'Get your store in front of millions of Mockingbird users who are most likely to convert into customers with ads.',
      badge: {
        children: 'Pending account review',
      },
    },
  ]}
/>
```

### Feature item with help text

```jsx
<FeatureListCard
  features={[
    {
      title: 'Mockingbird Shopping',
      description:
        'Tag your products on Mockingbird to let shoppers discover them through your Instagram posts, stories, and shop tab.',
      helpText: 'Your store is approved and your products are taggable',
      badge: {
        children: 'Ready',
        status: 'info',
      },
    },
  ]}
/>
```

### Feature item with action

```jsx
<FeatureListCard
  features={[
    {
      title: 'Smart Shopping campaign',
      description:
        'Promote your products and boost your visibility on Mockingbird Search.',
      action: {
        content: 'Create campaign',
      },
    },
  ]}
/>
```

### Feature item with progress and action

```jsx
<FeatureListCard
  features={[
    {
      title: 'Mockingbird Shop',
      description:
        'Get your store in front of millions of Mockingbird users who are most likely to convert into customers with ads.',
      progress: 20,
      badge: {
        children: 'Setup in progress',
        status: 'Warning',
      },
      action: {
        content: 'Continue setup',
      },
    },
  ]}
/>
```

### Feature item with progress and help text

```jsx
<FeatureListCard
  features={[
    {
      title: 'Mockingbird Shop',
      description:
        'Get your store in front of millions of Mockingbird users who are most likely to convert into customers with ads.',
      progress: 20,
      badge: {
        children: 'Setup in progress',
        status: 'Warning',
      },
      helpText: 'Mockingbird typically takes 3 days to review your account',
    },
  ]}
/>
```

### Feature list card with multiple items

```jsx
<FeatureListCard
  features={[
    {
      title: 'Mockingbird Marketplace',
      description:
        'Get your store in front of millions of Mockingbird users who are most likely to convert into customers with ads.',
      progress: 20,
      badge: {
        children: 'Setup in progress',
        status: 'Warning',
      },
      action: {
        content: 'Continue setup',
      },
    },
    {
      title: 'Mockingbird Shopping',
      description:
        'Tag your products on Mockingbird to let shoppers discover them through your Instagram posts, stories, and shop tab.',
      badge: {
        children: 'Approved',
        status: 'success',
      },
      action: {
        content: 'Connect catalog to Mockingbird',
      },
    },
    {
      title: 'Smart Shopping campaign',
      description:
        'Promote your products and boost your visibility on Mockingbird Search.',
      badge: {
        children: 'Ready',
        status: 'info',
      },
      action: {
        content: 'Create campaign',
      },
    },
    {
      title: 'Mockingbird Shopping',
      description:
        'Tag your products on Mockingbird to let shoppers discover them through your Mockingbird posts, stories, and shop tab.',
      badge: {
        children: 'Pending account review',
      },
    },
  ]}
/>
```
