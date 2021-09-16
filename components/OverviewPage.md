---
name: OverviewPage
---

# Overview page

Used to build the outer wrapper and sections of the overview page, including the page title, content, and footer. It gives merchants a central place for management, discovery, and education to help them succeed with the channel.

---

## Props

| Name     | Type      | Description                              | Required |
| -------- | --------- | ---------------------------------------- | -------- |
| title    | string    | Page title, in large type                | Yes      |
| children | ReactNode | The contents of the page                 | Yes      |
| footer   | ReactNode | The content displayed in the footer help |          |

### OverviewPage.Section

| Name     | Type      | Description                               | Required |
| -------- | --------- | ----------------------------------------- | -------- |
| title    | string    | Section title, in medium type             |          |
| children | ReactNode | The content to display inside the section | Yes      |

---

## Best practices

The overview page component should:

- Always provide a title for the page header
- The structure of the children is moderately flexible, but suggested to maintain the hierarchy of components. The `OverviewPage.Section` component is available to add optionally titled sections to the page.
- Use the footer to direct merchants to help documentation related to the channel

---

## Content guidelines

### Title

- Recommended title: "[channel name] channel overview”
- Flexibility in voice and tone to match the channel’s brand, if desired.

### Footer

The footer should link to information in the channel's help documentation and should follow this content pattern:

- Learn more about {channel}.
- What is {channel}?

---

## Examples

### Basic overview page

```jsx
<OverviewPage title="Mockingbird channel overview">Page content</OverviewPage>
```

### Overview page with footer

```jsx
<OverviewPage
  title="Mockingbird channel overview"
  footer="What is Mockingbird?"
>
  Page content
</OverviewPage>
```

### Overview page with sections

```jsx
<OverviewPage title="Mockingbird channel overview">
  <OverviewPage.Section title="Section 1">
    Section 1 contents
  </OverviewPage.Section>
  <OverviewPage.Section title="Section 2">
    Section 2 contents
  </OverviewPage.Section>
</OverviewPage>
```

### Overview page with sections and footer

```jsx
<OverviewPage
  title="Mockingbird channel overview"
  footer="What is Mockingbird?"
>
  <OverviewPage.Section title="Section 1">
    Section 1 contents
  </OverviewPage.Section>
  <OverviewPage.Section title="Section 2">
    Section 2 contents
  </OverviewPage.Section>
</OverviewPage>
```
