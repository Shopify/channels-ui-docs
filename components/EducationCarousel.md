---
name: EducationCarousel
---

# Education carousel

A carousel to display educational information on how to succeed with the channel.

Related Polaris components: [Card](https://polaris.shopify.com/components/layout-and-structure/legacy-card)

---

## Props

| Prop name | Type    | Description                               | Required |
| --------- | ------- | ----------------------------------------- | -------- |
| slides    | Slide[] | List of slides to display in the carousel | Yes      |

### Slide

| Name        | Type      | Description                                    | Required |
| ----------- | --------- | ---------------------------------------------- | -------- |
| title       | string    | The heading content of the card                | Yes      |
| description | string    | The body content of the card                   | Yes      |
| action      | Action    | The call to action, rendered as a plain button |          |
| media       | ReactNode | The visual media to display in the card        |          |

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

Education cards can contain tips, which are bite-sized information pieces with no rich media. They can also contain extended pieces of content, that include a link to external resources, such as videos and articles. The link can open as a modal, modal with a video, or an external site.

In total, use no more than 9-10 cards to not overwhelm the merchant. The cards that are most relevant to the merchant should appear at the beginning of the list.

### Smart recommendation system for educational content

Personalized cards can show up based on segments or activated by the events you define. For instance, how new the store is, its sales band, type of products, or location. If there are no triggers tied to personalized cards, you can show generic cards instead.

---

## Examples

### Text only slides

```jsx
<EducationCarousel
  slides={[
    {
      title: 'Use descriptions to help your products rank in search',
      description:
        'Ensure your products are extensive so they appear when buyers are searching on Mockingbird.',
    },
    {
      title: 'Add product images to make your listing more engaging',
      description:
        '10 of your products don’t have product images. Add an image to ensure your product sells better.',
    },
    {
      title: 'Use the right product photography',
      description:
        'Make sure your product stand out by uploading images on a white background',
    },
    {
      title:
        'Add Mockingbird product tags so your products are categorized correctly',
      description:
        '20 of your products don’t have product tags. Add tags to your products to ensure they appear in the right categories.',
    },
  ]}
/>
```

### Slides with actions

```jsx
<EducationCarousel
  slides={[
    {
      title: 'Use descriptions to help your products rank in search',
      description:
        'Ensure your products are extensive so they appear when buyers are searching on Mockingbird.',
      action: {
        content: 'Learn more',
      },
    },
    {
      title: 'Add product images to make your listing more engaging',
      description:
        '10 of your products don’t have product images. Add an image to ensure your product sells better.',
      action: {
        content: 'Read article',
      },
    },
    {
      title: 'Use the right product photography',
      description:
        'Make sure your product stand out by uploading images on a white background.',
      action: {
        content: 'Read article',
      },
    },
    {
      title: 'Add Mockingbird product tags',
      description:
        '20 of your products don’t have Mockingbird tags. Add tags to your products to ensure they appear in the right categories.',
      action: {
        content: 'Learn more',
      },
    },
  ]}
/>
```

### Slides with media

```jsx
<EducationCarousel
  slides={[
    {
      title: 'Use descriptions to help your products rank in search',
      description:
        'Ensure your products are extensive so they appear when buyers are searching on Mockingbird.',
      media: (
        <img
          style={{
            width: '100%',
            height: '100%',
            objectFit: 'cover',
            objectPosition: 'center',
          }}
          src="https://burst.shopifycdn.com/photos/programmer-focused-on-code.jpg?width=373"
        />
      ),
    },
    {
      title: 'Add product images to make your listing more engaging',
      description:
        '10 of your products don’t have product images. Add an image to ensure your product sells better.',
      media: (
        <img
          style={{
            width: '100%',
            height: '100%',
            objectFit: 'cover',
            objectPosition: 'center',
          }}
          src="https://burst.shopifycdn.com/photos/photography-studio.jpg?width=373"
        />
      ),
    },
    {
      title: 'Use the right product photography',
      description:
        'Make sure your product stand out by uploading images on a white background.',
      media: (
        <img
          style={{
            width: '100%',
            height: '100%',
            objectFit: 'cover',
            objectPosition: 'bottom',
          }}
          src="https://burst.shopifycdn.com/photos/product-photography-camera.jpg?width=373"
        />
      ),
    },
    {
      title: 'Add Mockingbird product tags',
      description:
        '20 of your products don’t have Mockingbird tags. Add tags to your products to ensure they appear in the right categories.',
      media: (
        <img
          style={{
            width: '100%',
            height: '100%',
            objectFit: 'cover',
            objectPosition: 'center',
          }}
          src="https://burst.shopifycdn.com/photos/laptop-from-above.jpg?width=373"
        />
      ),
    },
  ]}
/>
```

### Slides with media and actions

```jsx
<EducationCarousel
  slides={[
    {
      title: 'Use descriptions to help your products rank in search',
      description:
        'Ensure your products are extensive so they appear when buyers are searching on Mockingbird.',
      media: (
        <img
          style={{
            width: '100%',
            height: '100%',
            objectFit: 'cover',
            objectPosition: 'center',
          }}
          src="https://burst.shopifycdn.com/photos/programmer-focused-on-code.jpg?width=373"
        />
      ),
      action: {
        content: 'Learn more',
      },
    },
    {
      title: 'Add product images to make your listing more engaging',
      description:
        '10 of your products don’t have product images. Add an image to ensure your product sells better.',
      media: (
        <img
          style={{
            width: '100%',
            height: '100%',
            objectFit: 'cover',
            objectPosition: 'center',
          }}
          src="https://burst.shopifycdn.com/photos/photography-studio.jpg?width=373"
        />
      ),
      action: {
        content: 'Read article',
      },
    },
    {
      title: 'Use the right product photography',
      description:
        'Make sure your product stand out by uploading images on a white background.',
      media: (
        <img
          style={{
            width: '100%',
            height: '100%',
            objectFit: 'cover',
            objectPosition: 'bottom',
          }}
          src="https://burst.shopifycdn.com/photos/product-photography-camera.jpg?width=373"
        />
      ),
      action: {
        content: 'Read article',
      },
    },
    {
      title: 'Add Mockingbird product tags',
      description:
        '20 of your products don’t have Mockingbird tags. Add tags to your products to ensure they appear in the right categories.',
      media: (
        <img
          style={{
            width: '100%',
            height: '100%',
            objectFit: 'cover',
            objectPosition: 'center',
          }}
          src="https://burst.shopifycdn.com/photos/laptop-from-above.jpg?width=373"
        />
      ),
      action: {
        content: 'Learn more',
      },
    },
  ]}
/>
```

### Education carousel with mixed slides

```jsx
<EducationCarousel
  slides={[
    {
      title: 'Use descriptions to help your products rank in search',
      description:
        'Ensure your products are extensive so they appear when buyers are searching on Mockingbird.',
      media: (
        <img
          style={{
            width: '100%',
            height: '100%',
            objectFit: 'cover',
            objectPosition: 'center',
          }}
          src="https://burst.shopifycdn.com/photos/programmer-focused-on-code.jpg?width=373"
        />
      ),
    },
    {
      title: 'Add product images to make your listing more engaging',
      description:
        '10 of your products don’t have product images. Add an image to ensure your product sells better.',
      action: {
        content: 'Read article',
      },
    },
    {
      title: 'Use the right product photography',
      description:
        'Make sure your product stand out by uploading images on a white background.',
      media: (
        <img
          style={{
            width: '100%',
            height: '100%',
            objectFit: 'cover',
            objectPosition: 'bottom',
          }}
          src="https://burst.shopifycdn.com/photos/product-photography-camera.jpg?width=373"
        />
      ),
      action: {
        content: 'Read article',
      },
    },
    {
      title: 'Add Mockingbird product tags',
      description:
        '20 of your products don’t have Mockingbird tags. Add tags to your products to ensure they appear in the right categories.',
    },
  ]}
/>
```
