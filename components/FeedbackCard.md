---
name: FeedbackCard
---

# Feedback card

A feedback card is used if you want to get merchant feedback about the launch of your channel or a new feature.

---

## Props

| Name     | Type      | Description                         | Default | Required |
| -------- | --------- | ----------------------------------- | ------- | -------- |
| children | ReactNode | Main content to display in the card |         | Yes      |

---

## Best practices

- This component should be only be surfaced at the bottom of the overview page, and can be rendered in its own `OverviewPage.Section`.
- The children should contain a link out to a feedback form that you own or can open an `EmbeddedModal` that contains the form.
- Asking for feedback can be done independently of offering support but should be used deliberately.
- It should only be surface for the launch of a new channel or a major features. It should be timeboxed and not used forever, with a recommended maximum of 2 months.
- Incoming feedback should be actively monitored by your team and grouped into themes for further action.

---

## Examples

### Basic feedback card

```jsx
<FeedbackCard>
  <p>
    Let us know what you think of the redesigned Overview page.{' '}
    <Link>Give feedback</Link>
  </p>
</FeedbackCard>
```
