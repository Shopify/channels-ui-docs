---
name: SettingsPage
---

# Settings page

After merchants onboard onto your channel, they should be able to access their accounts and other settings related to your channel in the settings section. The settings section should be accessible via a nav item nested below your channel in the Shopify admin left navigation.

---

## Props

| Name     | Type      | Description                                  | Required |
| -------- | --------- | -------------------------------------------- | -------- |
| title    | string    | Page title, in large type                    | Yes      |
| children | ReactNode | The contents of the page                     | Yes      |
| navItems | Item[]    | List of nav items for your settings sections |          |
| footer   | ReactNode | The content displayed in the footer help     |          |

### Item

| Name   | Type       | Description                                             | Required |
| ------ | ---------- | ------------------------------------------------------- | -------- |
| icon   | IconSource | Icon displayed by the nav item                          | Yes      |
| label  | string     | Text displayed for the nav item                         | Yes      |
| url    | string     | A location for the nav item to navigate to when clicked | Yes      |
| active | boolean    | Whether the merchant is currently on this settings page |          |

### SettingsPage.Section

| Name        | Type      | Description                                    | Required |
| ----------- | --------- | ---------------------------------------------- | -------- |
| title       | string    | Section title, in medium type                  | Yes      |
| description | string    | Section description, displayed below the title |          |
| children    | ReactNode | The content to display inside the section      | Yes      |

---

## Best practices

There are 2 variations of the settings page depending on how many settings your channel has.

### Simplified settings page

This version can be used when your channel doesn't have too many settings. This settings page is more minimalistic and only has a single page to display.

- The section title should speak to the type of settings. Example: Accounts
- The section description should explain what the settings are.
- Multiple sections can be rendered on a page. Common settings should be grouped together into a section, such as Accounts and Personal info, Shipping and Delivery.

### Complex settings page

Use this version when the channel offers multiple features and capabilities, like marketing and selling. The navigation is a way to help group common settings together to help merchants navigate through them easier. Each navigation item should correspond to a different settings page. Examples `/settings/marketing`, `/settings/selling`

- Keep navigation item labels to 1–3 words max to ensure local translations will have enough space.
- Only a single section should be rendered on a page.
- Make sure the section title explicitly describes the type of settings. Example: Marketing
- Use the section description to tell merchants what types of settings they are seeing.

---

## Examples

### Simple settings page

```jsx
<SettingsPage title="Settings">
  <SettingsPage.Section
    title="Section title"
    description="Text to describe this section of the settings. You may only have one section and that’s okay too."
  >
    <Card sectioned>Setting 1</Card>
    <Card sectioned>Setting 2</Card>
    <Card sectioned>Setting 3</Card>
  </SettingsPage.Section>
  <SettingsPage.Section
    title="Section title"
    description="Text to describe this section of the settings. You may only have one section and that’s okay too."
  >
    <Card sectioned>Setting 1</Card>
    <Card sectioned>Setting 2</Card>
  </SettingsPage.Section>
</SettingsPage>
```

### Settings page with footer

```jsx
<SettingsPage title="Settings" footer="What is Mockingbird?">
  <SettingsPage.Section
    title="Section title"
    description="Text to describe this section of the settings. You may only have one section and that’s okay too."
  >
    <Card sectioned>Setting 1</Card>
    <Card sectioned>Setting 2</Card>
    <Card sectioned>Setting 3</Card>
  </SettingsPage.Section>
  <SettingsPage.Section
    title="Section title"
    description="Text to describe this section of the settings. You may only have one section and that’s okay too."
  >
    <Card sectioned>Setting 1</Card>
    <Card sectioned>Setting 2</Card>
  </SettingsPage.Section>
</SettingsPage>
```

### Complex settings page

```jsx
<SettingsPage
  title="Settings"
  navItems={[
    {
      icon: ProfileMajor,
      label: 'Account',
      url: '/settings/account',
    },
    {
      icon: MarketingMajor,
      label: 'Marketing',
      url: '/settings/marketing',
      active: true,
    },
    {
      icon: OnlineStoreMajor,
      label: 'Commerce',
      url: '/settings/commerce',
    },
    {
      icon: ExchangeMajor,
      label: 'Data sharing',
      url: '/settings/data',
    },
  ]}
>
  <SettingsPage.Section
    title="Commerce settings"
    description="Text to describe this section of the settings. These are marketing
    settings shared across Mockingbird Marketplace and Mockingbird
    Photos."
  >
    <Card sectioned>Setting 1</Card>
    <Card sectioned>Setting 2</Card>
    <Card sectioned>Setting 3</Card>
  </SettingsPage.Section>
</SettingsPage>
```
