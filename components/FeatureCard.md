---
name: FeatureCard
---

# Feature card

Feature cards are used to advertise and explain a feature or an offer of the channel. It’s a starting point of a merchant’s onboarding. A feature card may appear on the Introduction page and the Overview page of a channel.

---

## Props

| Name            | Type           | Description                                              | Default | Required |
| --------------- | -------------- | -------------------------------------------------------- | ------- | -------- |
| children        | ReactNode      | The visual media to display in the card                  |         | Yes      |
| title           | string         | The card heading content                                 |         | Yes      |
| titleElement    | HeadingTagName | The card heading element                                 | h2      |          |
| feature         | string         | The card subheading content                              |         | Yes      |
| featureElement  | HeadingTagName | The card subheading element                              | h3      |          |
| description     | string         | The card body content                                    |         | Yes      |
| primaryAction   | Action         | The main call to action, rendered as a basic button      |         | Yes      |
| secondaryAction | Action         | The secondary call to action, rendered as a plain button |         |          |
| portrait        | boolean        | Whether the card content should be laid out vertically   | false   |          |
| badgeText       | string         | Text to render in the badge                              |         |          |

HeadingTagName = 'h1' | 'h2' | 'h3' | 'h4' | 'h5' | 'h6' | 'p'

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

- The first feature you show should fit the largest number of merchants e.g. “Free organic search” is suitable for any merchant at any stage of the business.
- If the merchant arrived from a specific callout (like marketing or blog), dynamically place the feature mentioned in the callout at the top.
- Use badges to provide hierarchy and adapt to merchant’s unique needs.

---

## Content guidelines

### Feature name

- Placed above the task title, in a smaller font.
- Use the same name that’s used on your platform.
- Use one feature name everywhere in the channel.

### Task title

- Verb-driven and tells a merchant what task they can accomplish by onboarding to it.
- Typically doesn’t include the name of the feature, to avoid repetition.

### Value proposition

- 1-2 sentences to elaborate on the task title and explain what the feature will do for the merchant.
- Try to be descriptive and avoid marketing fluff vocabulary (amazing, beautiful, etc.)
- Example:
  - “Tag your products on Instagram to let shoppers discover them through your Instagram posts, stories, and shop tab.”

### Call to action

- Recommended CTA is “Start setup.”
- If you choose a different CTA, follow the verb+noun pattern. Make sure it’s clear that they’re about to onboard to the feature.
- CTAs can be dynamic to account for merchants returning after abandoning the setup process.

### Badge (Optional)

- Help merchants quickly decide to start with this feature.
- Badge options: Recommended, Free, Paid, etc.

## Visual guidelines

- If a channel has only 1 feature, use a large image.
- For multi-feature layouts, use square images.
- Consider focal points as it crops/scales on mobile.
- Create a separate image if going from 1 feature to multiple, to avoid skewed cropping.

### Flexibility

- Can be different between channels, depending on brand style.
- Keep the illustrations descriptive, abstract images can make it difficult for merchants to understand the value proposition.
- Visual could be an image, video, or illustration.
- Use as an opportunity to show merchants the ready state of the feature/task. For instance, show how an ad might look on the platform.

---

## Examples

### Basic feature card

```jsx
<FeatureCard
  title="Sell your products on Mockingbird"
  feature="Mockingbird shop"
  description="Bring the look and feel of your Shopify store to Mockingbird Shops, and create custom collections."
  primaryAction={{
    content: 'Start setup',
  }}
>
  <img
    alt=""
    width="100%"
    height="100%"
    style={{
      objectFit: 'cover',
      objectPosition: 'center',
    }}
    src="https://burst.shopifycdn.com/photos/woman-holding-phone-browsing-social-media.jpg?width=500"
  />
</FeatureCard>
```

### Feature card with secondary action

```jsx
<FeatureCard
  title="Sell your products on Mockingbird"
  feature="Mockingbird shop"
  description="Bring the look and feel of your Shopify store to Mockingbird Shops, and create custom collections."
  primaryAction={{
    content: 'Start setup',
  }}
  secondaryAction={{
    content: 'Learn more',
  }}
>
  <img
    alt=""
    width="100%"
    height="100%"
    style={{
      objectFit: 'cover',
      objectPosition: 'center',
    }}
    src="https://burst.shopifycdn.com/photos/woman-holding-phone-browsing-social-media.jpg?width=500"
  />
</FeatureCard>
```

### Feature card with badge

```jsx
<FeatureCard
  title="Sell your products on Mockingbird"
  feature="Mockingbird shop"
  description="Bring the look and feel of your Shopify store to Mockingbird Shops, and create custom collections."
  primaryAction={{
    content: 'Start setup',
  }}
  badgeText="Free"
>
  <img
    alt=""
    width="100%"
    height="100%"
    style={{
      objectFit: 'cover',
      objectPosition: 'center',
    }}
    src="https://burst.shopifycdn.com/photos/woman-holding-phone-browsing-social-media.jpg?width=500"
  />
</FeatureCard>
```

### Feature card with badge and secondary action

```jsx
<FeatureCard
  title="Sell your products on Mockingbird"
  feature="Mockingbird shop"
  description="Bring the look and feel of your Shopify store to Mockingbird Shops, and create custom collections."
  primaryAction={{
    content: 'Start setup',
  }}
  secondaryAction={{
    content: 'Learn more',
  }}
  badgeText="Free"
>
  <img
    alt=""
    width="100%"
    height="100%"
    style={{
      objectFit: 'cover',
      objectPosition: 'center',
    }}
    src="https://burst.shopifycdn.com/photos/woman-holding-phone-browsing-social-media.jpg?width=500"
  />
</FeatureCard>
```

### Feature card with a custom element

```jsx
<FeatureCard
  title="Sell your products on Mockingbird"
  feature="Mockingbird shop"
  description="Bring the look and feel of your Shopify store to Mockingbird Shops, and create custom collections."
  primaryAction={{
    content: 'Start setup',
  }}
  titleElement="h3"
  featureElement="h4"
>
  <img
    alt=""
    width="100%"
    height="100%"
    style={{
      objectFit: 'cover',
      objectPosition: 'center',
    }}
    src="https://burst.shopifycdn.com/photos/woman-holding-phone-browsing-social-media.jpg?width=500"
  />
</FeatureCard>
```

### Portrait feature card

```jsx
<FeatureCard
  title="Sell your products on Mockingbird"
  feature="Mockingbird shop"
  description="Bring the look and feel of your Shopify store to Mockingbird Shops, and create custom collections."
  primaryAction={{
    content: 'Start setup',
  }}
  portrait
>
  <img
    alt=""
    width="100%"
    height="100%"
    style={{
      objectFit: 'cover',
      objectPosition: 'center',
    }}
    src="https://burst.shopifycdn.com/photos/woman-holding-phone-browsing-social-media.jpg?width=500"
  />
</FeatureCard>
```

## Accessibility

The required `title` prop gives the feature card title a level 2 heading (`h2`) by default, which should match the semantic structure of the Introduction page. The heading level can be configured using the `titleElement` prop, and should be set to `h3` if being used on the Overview page.

The required `feature` prop gives the feature card subheading a level 3 heading (`h3`) by default, which should match the semantic structure of the Introduction page. The heading level can be configured using the `featureElement` prop, and should be set to `h4` if being used on the Overview page.
