---
name: IntroductionPage
---

# Introduction page

An introduction page is a welcome screen of a channel. Its main goal is to help a merchant understand the value of the channel and choose the right starting point.

The structure of the page depends on the number of features a channel has to offer. Separate features allow merchants to choose a specific promotion or product placement they want to set up first. In a nutshell, a feature is a tool you offer merchants to interact with and succeed on your platform.

---

## Props

| Name     | Type      | Description                              | Required |
| -------- | --------- | ---------------------------------------- | -------- |
| title    | string    | Page title, in large type                | Yes      |
| children | ReactNode | The contents of the page                 | Yes      |
| footer   | ReactNode | The content displayed in the footer help |          |

---

## Best practices

- If a channel offers access to an external marketplace, it’s a single-feature channel. You can choose to have an intro page with a single large feature card to show the benefits of the channel or even no intro page at all.
- If a channel has a number of separate offers, it's a multiple-feature channel.
- Display a max of 3 features on the introduction page to avoid information overload.
- If merchants don't want to onboard onto any feature and just need to sync their products with the platform, consider adding a link to do that below the feature cards.
- Lead with free features or those that require less upfront financial investment.

---

## Examples

### Basic introduction page

```jsx
<IntroductionPage title="Get start with the Mockingbird channel">
  Page content
</IntroductionPage>
```

### Introduction page with footer

```jsx
<IntroductionPage
  title="Get start with the Mockingbird channel"
  footer="What is Mockingbird?"
>
  Page content
</IntroductionPage>
```

### Single-feature introduction page

```jsx
<IntroductionPage
  title="Get start with the Mockingbird channel"
  footer="What is Mockingbird?"
>
  <FeatureCard
    title="Start by listing your products for free on Mockingbird Search"
    feature="Mockingbird free listings"
    description="Reach more customers by increasing the chances of your products appear in organic search results. Once your products are synced, you can also create Smart Shopping ads."
    primaryAction={{
      content: 'Start setup',
    }}
    secondaryAction={{
      content: 'Learn more',
    }}
    badgeText="Free"
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
</IntroductionPage>
```

### Multi-feature introduction page

```jsx
<IntroductionPage
  title="Where would you like to begin?"
  footer="What is Mockingbird?"
>
  <FeatureCard
    title="List your products for free on Mockingbird search"
    feature="Mockingbird free listings"
    description="Let customers easily search, discover, and buy your products across Mockingbird."
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
  <FeatureCard
    title="Create ads on Mockingbird"
    feature="Mockingbird paid ads"
    description="Get your store in front of millions of Mockingbird users who are most likely to convert into customers with ads."
    primaryAction={{
      content: 'Start setup',
    }}
    secondaryAction={{
      content: 'Learn more',
    }}
    badgeText="Paid"
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
  <FeatureCard
    title="Sell your products on Mockingbird"
    feature="Mockingbird instant shopping"
    description="Let customers discover and purchase your products directly from your Mockingbird posts. "
    primaryAction={{
      content: 'Start setup',
    }}
    secondaryAction={{
      content: 'Learn more',
    }}
    badgeText="Paid"
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
</IntroductionPage>
```
