---
name: AssetConnection
---

# Asset connection

The asset connection component is used when a merchant needs to select an asset tied to their global account on the platform. For example, the merchant may need to select a specific business or ad account to connect to Shopify.

---

## Props

| Prop name       | Type          | Optional |
| --------------- | ------------- | -------- |
| placeholderText | string        | false    |
| action          | ComplexAction | false    |
| items           | ItemProps[]   | true     |
| selectedItem    | string        | true     |
| connectedItem   | ConnectedItem | true     |

### ConnectedItem

| Prop name    | Type             | Optional |
| ------------ | ---------------- | -------- |
| title        | ReactNode        | false    |
| details      | string or Action | true     |
| avatarSource | string           | true     |

### ItemProps

| Prop name      | Type                 | Optional | Default |
| -------------- | -------------------- | -------- | ------- |
| id             | string               | false    |         |
| title          | string               | false    |         |
| onAction       | (id: string) => void | false    |         |
| details        | string               | true     |         |
| suggested      | boolean              | true     | false   |
| avatarSource   | string               | true     |         |
| disabled       | boolean              | true     | false   |
| disabledReason | string               | true     |         |

---

## Best practices

- This component should be rendered in a `Card` if displayed on the settings page
- This component should be rendered in a `CollapsibleCard` if displayed in an onboarding flow
  - The collapsible card should be marked as completed when the merchant has connected their account
  - The collapsible card action can be used to provide a way for the merchant to create a new asset account on the platform
- If there are no asset items:
  - The `placeholderText` prop should communicate that the merchant does not have any assets on the platform
  - The `action` prop should allow merchants to create a new asset account. This should be done automatically, or embedded in the channel where possible.
  - The merchant should still have to explicitly connect the newly created asset before continuing onboarding.
- If there is only a single asset item:
  - Do not automatically connect it, since the merchant should explicitly connect it
  - Do not provide the `suggested` prop with the item
- If there are multiple asset items:
  - The `placeholderText` should communicate that the merchant needs to select an asset item
  - The `suggested` item prop can be used to recommend that a merchant connects a specific asset.
- Provide a `disabledReason` for items that are disabled so merchants can understand why they are unable to pick a given asset.
- The `connectedItem` details prop can be used to link a merchant to the asset page on the platform.

---

## Examples

### Asset connection with no items

```jsx
<AssetConnection
  placeholderText="No businesses found"
  action={{
    content: 'Create new business',
  }}
/>
```

### Asset connection with a single item

```jsx
<AssetConnection
  placeholderText="Select a business"
  items={[
    {
      id: 'spectrally-yours',
      title: 'Spectrally Yours',
      details: '123456789',
      onAction: () => {},
      avatarSource:
        'https://burst.shopifycdn.com/photos/pale-pink-flower-with-water-drops.jpg?width=100',
    },
  ]}
  action={{
    content: 'Connect',
  }}
/>
```

### Asset connection with multiple items

```jsx
<AssetConnection
  placeholderText="Select a business"
  items={[
    {
      id: 'spectrally-yours',
      title: 'Spectrally Yours',
      details: '123456789',
      onAction: () => {},
      avatarSource:
        'https://burst.shopifycdn.com/photos/pale-pink-flower-with-water-drops.jpg?width=100',
    },
    {
      id: 'wootlot-boutique',
      title: 'Wootlot Boutique',
      details: '123456789',
      onAction: () => {},
    },
    {
      id: 'space-cadets',
      title: 'Space Cadets',
      details: '123456789',
      onAction: () => {},
    },
  ]}
  action={{
    content: 'Connect',
  }}
/>
```

### Asset connection with a disabled item

```jsx
<AssetConnection
  placeholderText="Select a business"
  items={[
    {
      id: 'spectrally-yours',
      title: 'Spectrally Yours',
      avatarSource:
        'https://burst.shopifycdn.com/photos/pale-pink-flower-with-water-drops.jpg?width=100',
      details: '123456789',
      onAction: () => {},
    },
    {
      id: 'wootlot-boutique',
      title: 'Wootlot Boutique',
      details: '123456789',
      onAction: () => {},
      disabled: true,
      disabledReason: 'This business does not have enough followers',
    },
    {
      id: 'space-cadets',
      title: 'Space Cadets',
      details: '123456789',
      onAction: () => {},
    },
  ]}
  action={{
    content: 'Connect',
  }}
/>
```

### Asset connection with a suggested item

```jsx
<AssetConnection
  placeholderText="Select a business"
  items={[
    {
      id: 'spectrally-yours',
      title: 'Spectrally Yours',
      avatarSource:
        'https://burst.shopifycdn.com/photos/pale-pink-flower-with-water-drops.jpg?width=373',
      details: '123456789',
      onAction: () => {},
      suggested: true,
    },
    {
      id: 'wootlot-boutique',
      title: 'Wootlot Boutique',
      details: '123456789',
      onAction: () => {},
    },
    {
      id: 'space-cadets',
      title: 'Space Cadets',
      details: '123456789',
      onAction: () => {},
    },
  ]}
  action={{
    content: 'Connect',
  }}
/>
```

### Asset connection with a selected item

```jsx
<AssetConnection
  placeholderText="Select a business"
  selectedItem="spectrally-yours"
  items={[
    {
      id: 'spectrally-yours',
      title: 'Spectrally Yours',
      avatarSource:
        'https://burst.shopifycdn.com/photos/pale-pink-flower-with-water-drops.jpg?width=373',
      details: '123456789',
      onAction: () => {},
    },
    {
      id: 'wootlot-boutique',
      title: 'Wootlot Boutique',
      details: '123456789',
      onAction: () => {},
    },
    {
      id: 'cadets',
      title: 'Cadets',
      details: '123456789',
      onAction: () => {},
    },
  ]}
  action={{
    content: 'Connect',
  }}
/>
```

### Asset connection with a connected item

```jsx
<AssetConnection
  placeholderText="Select a business"
  connectedItem={{
    title: 'Spectrally Yours',
    details: {
      content: '12345678',
    },
    avatarSource:
      'https://burst.shopifycdn.com/photos/pale-pink-flower-with-water-drops.jpg?width=373',
  }}
  action={{
    content: 'Switch',
  }}
/>
```
