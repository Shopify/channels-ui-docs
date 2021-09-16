---
name: EmbeddedVideo
---

# Embedded video

Component for rendering a video thumbnail that opens a video in an embedded modal.

---

## Props

| Name         | Type   | Description                                                          | Default           | Required |
| ------------ | ------ | -------------------------------------------------------------------- | ----------------- | -------- |
| thumbnailUrl | string | URL source for the thumbnail image                                   |                   | Yes      |
| videoUrl     | string | URL source for the video                                             |                   | Yes      |
| modalTitle   | string | The title content for the modal                                      |                   | Yes      |
| modalAction  | Action | The call to action, rendered as a primary button in the modal footer |                   | Yes      |
| videoTitle   | string | The title of the video's iframe                                      |                   | Yes      |
| videoLength  | number | The length of the video in seconds                                   |                   |          |
| modalSrc     | string | App route where the modal contents are rendered                      | `/embedded_modal` |          |

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

## Usage

Component renders a video thumbail that will trigger a modal at local route of `/embedded_modal` on click. It uses message events to link it to the embedded app and deploy a portal to render the provided video url as an iframe.

#### Within App

```jsx
<EmbeddedVideo
  thumbnailUrl="https://burst.shopifycdn.com/photos/woman-edits-images-on-her-laptop.jpg?width=375"
  videoLength={107}
  modalTitle="Learn more about Smart Shopping"
  modalAction={{
    content: 'Done',
  }}
  videoUrl="https://www.youtube.com/embed/AYlX7fjbwUQ?enablejsapi=1&rel=0&modestbranding=1&playsinline=1"
  videoTitle="Smart shopping introduction"
/>
```

## Best practices

- Modal is configured to deploy at `/embedded_modal`, but can be adjusted via `modalSrc` prop
- Modal height can be configured via `setupModalAutoSizing` method from `app-bridge-utils` (from within `/embedded_modal` window)
- YouTube videos can be embedded using the following url structure: `https://www.youtube.com/embed/${youtubeId}?enablejsapi=1&rel=0&modestbranding=1&playsinline=1`

---

## Accessibility

The `videoTitle` prop is used as the title of the `iframe` with the `videoUrl` as the `src`.
