---
name: OnboardingIntro
---

# Onboarding intro

This component serves two purposes:

- To remind merchants of their choice of the feature so they know they’re onboarding to the right thing
- To provide additional information on the feature.

You can include additional images or a built-in video introducing the feature/channel itself. It’s also important to include information on what the merchant will be able to do once they onboard.

---

## Props

| Name      | Type      | Description                                  | Default | Required |
| --------- | --------- | -------------------------------------------- | ------- | -------- |
| children  | ReactNode | Main content to display in the card          |         | Yes      |
| action    | Action    | Call to action, rendered as a primary button |         | Yes      |
| media     | ReactNode | Visual media to display in the card section  |         |          |
| completed | boolean   | Whether the step is completed                | false   |          |

---

## Best practices

- This component should be rendered inside an `OnboardingCard`
- The media can be an image or video. Videos should use the `EmbeddedVideo` component so the merchant is able to view the video without leaving the onboarding flow.
- The `action` is used to render a button that the merchant can click to indicate they understand the content presented in the introduction. Once the merchant has clicked the action, the step should be marked as completed and the button will not be rendered.

---

## Examples

### Basic onboarding intro

```jsx
<OnboardingIntro
  action={{
    content: 'I understand',
  }}
>
  <p>
    Once you’ve completed this setup, you will be able to create a Smart
    Shopping campaign. Smart Shopping campaigns can be used to promote your
    products and boost their visibility on Mockingbird Search.
  </p>
</OnboardingIntro>
```

### Onboarding intro with media

```jsx
<OnboardingIntro
  media={
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
  }
  action={{
    content: 'I understand',
  }}
>
  <p>
    Once you’ve completed this setup, you will be able to create a Smart
    Shopping campaign. Smart Shopping campaigns can be used to promote your
    products and boost their visibility on Mockingbird Search.
  </p>
</OnboardingIntro>
```

### Completed onboarding intro

```jsx
<OnboardingIntro
  media={
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
  }
  action={{
    content: 'I understand',
  }}
  completed
>
  <p>
    Once you’ve completed this setup, you will be able to create a Smart
    Shopping campaign. Smart Shopping campaigns can be used to promote your
    products and boost their visibility on Mockingbird Search.
  </p>
</OnboardingIntro>
```
