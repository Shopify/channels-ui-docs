---
name: ProductStatusSection
---

# Product status section

This component gives merchants an overview of their products and their status on the channel. Merchants should be able to quickly glance at the card and understand which of their products are in good standing, versus requiring additional attention to get them successfully synced onto the channel.

---

## Props

| Prop name       | Type   | Optional |
| --------------- | ------ | -------- |
| summary         | string | false    |
| manageAction    | Action | false    |
| productStatuses | Status | false    |
| helpText        | string | true     |
| tips            | Tips   | true     |

### Tips

| Prop name | Type      | Optional |
| --------- | --------- | -------- |
| title     | string    | true     |
| children  | ReactNode | false    |

### Status

| Props name | Type             |
| ---------- | ---------------- |
| badge      | BadgeProp        |
| label      | Action OR string |

### BadgeProp

| Prop name | Type        | Optional |
| --------- | ----------- | -------- |
| status    | BadgeStatus | true     |
| children  | string      | false    |

BadgeStatus = 'success' | 'info' | 'attention' | 'critical' | 'warning' | 'new'

---

## Best practices

- Include the number of products in each status category, to the given limit (250+)
- Product counts link to either your own product table if you’re creating one for the channel or to the general bulk editor.
- Standard set of product statuses are: Approved, Pending, Not approved.
- Additional statuses can be used if your channel has a status that doesn’t fall under any of the three categories. The title of the additional pill can be customized e.g. Approved for ads, Approved for marketing, Partially approved.
- Use a card footer to set expectations around how long they may have to wait for product review or any other vital product information.
- You can use the tips section to help merchants successfully sync their products
  - Tips are text only.
  - Small, actionable pieces of content.
  - Can be data-driven and use merchant’s information from the channel to help them make the right decision or take a specific action.
  - Can contain a link to learn more about the subject.

---

## Examples

### Basic product status section

```jsx
<ProductStatusSection
  summary="99 products synced to Mockingbird"
  manageAction={{content: 'Manage availability'}}
  productStatuses={[
    {
      badge: {
        children: 'Approved',
        status: 'success',
      },
      label: {
        content: '90 products',
        url: 'https://shopify.com',
        external: true,
      },
    },
    {
      badge: {
        children: 'Pending',
      },
      label: '0 products',
    },
    {
      badge: {
        children: 'Not approved',
        status: 'critical',
      },
      label: {
        content: '9 products',
        url: 'https://shopify.com',
        external: true,
      },
    },
  ]}
/>
```

### Product status section with help text

```jsx
<ProductStatusSection
  summary="99 products synced to Mockingbird"
  manageAction={{content: 'Manage availability'}}
  productStatuses={[
    {
      badge: {
        children: 'Approved',
        status: 'success',
      },
      label: {
        content: '90 products',
        url: 'https://shopify.com',
        external: true,
      },
    },
    {
      badge: {
        children: 'Pending',
      },
      label: '0 products',
    },
    {
      badge: {
        children: 'Not approved',
        status: 'critical',
      },
      label: {
        content: '9 products',
        url: 'https://shopify.com',
        external: true,
      },
    },
  ]}
  helpText="Mockingbird usually takes 3-5 days to review products"
/>
```

### Product status section with tips

```jsx
<ProductStatusSection
  summary="99 products synced to Mockingbird"
  manageAction={{content: 'Manage availability'}}
  productStatuses={[
    {
      badge: {
        children: 'Approved',
        status: 'success',
      },
      label: {
        content: '90 products',
        url: 'https://shopify.com',
        external: true,
      },
    },
    {
      badge: {
        children: 'Pending',
      },
      label: '0 products',
    },
    {
      badge: {
        children: 'Not approved',
        status: 'critical',
      },
      label: {
        content: '9 products',
        url: 'https://shopify.com',
        external: true,
      },
    },
  ]}
  tips={{
    title: 'Tips to optimize your products',
    children: (
      <div>
        Use relevant keywords in your product title and description. Product
        images should be on a white background with no logos. Your GTIN should
        be a valid Global Trade Item Number, not an SKU.
      </div>
    ),
  }}
/>
```

### Product status section with custom statuses

```jsx
<ProductStatusSection
  summary="99 products synced to Mockingbird"
  manageAction={{content: 'Manage availability'}}
  productStatuses={[
    {
      badge: {
        children: 'Approved for marketplace',
        status: 'success',
      },
      label: {
        content: '90 products',
        url: 'https://shopify.com',
        external: true,
      },
    },
    {
      badge: {
        children: 'Approved for ads',
        status: 'success',
      },
      label: {
        content: '98 products',
        url: 'https://shopify.com',
        external: true,
      },
    },
    {
      badge: {
        children: 'Pending',
      },
      label: '0 products',
    },
    {
      badge: {
        children: 'Rejected for marketplace',
        status: 'critical',
      },
      label: {
        content: '9 products',
        url: 'https://shopify.com',
        external: true,
      },
    },
    {
      badge: {
        children: 'Rejected for ads',
        status: 'critical',
      },
      label: {
        content: '1 products',
        url: 'https://shopify.com',
        external: true,
      },
    },
  ]}
/>
```
