---
name: EmbeddedModal
---

# EmbeddedModal

Component for rendering modals via app-bridge from within embedded apps.

---

## Props

| Prop name       | Type            | Description                                             | Default           | Required |
| --------------- | --------------- | ------------------------------------------------------- | ----------------- | -------- |
| open            | boolean         | Whether the modal is open or not                        |                   | Yes      |
| src             | string          | The url that will be loaded as the content of the modal | '/embedded_modal' |          |
| children        | ReactNode       | The content to display inside the modal                 |                   |          |
| title           | string          | The title of the modal                                  |                   |          |
| size            | Size            | Controls the size of the modal                          |                   |          |
| sectioned       | boolean         | Whether the children are wrapped in a card section      |                   |          |
| primaryAction   | ComplexAction   | Primary action displayed in the modal footer            |                   |          |
| secondaryAction | ComplexAction[] | List of secondary actions displayed in the modal footer |                   |          |
| footer          | ReactNode       | Content to display on the left side of the footer       |                   |          |
| onClose         | () => void      | Callback when the modal is closed                       |                   |          |

Size = "Small" | "Medium" | "Large"

### ComplexAction

| Name               | Type       | Description                                                  |
| ------------------ | ---------- | ------------------------------------------------------------ |
| id                 | string     | A unique identifier for the action                           |
| content            | string     | Content the action displays                                  |
| accessibilityLabel | string     | Visually hidden text for screen readers                      |
| url                | string     | A destination to link to                                     |
| external           | boolean    | Forces url to open in a new tab                              |
| onAction           | () => void | Callback when an action takes place                          |
| onMouseEnter       | () => void | Callback when mouse enter                                    |
| onTouchStart       | () => void | Callback when element is touched                             |
| disabled           | boolean    | Whether the action is disabled                               |
| destructive        | boolean    | Whether the action is destructive                            |
| icon               | IconSource | Source of the icon                                           |
| outline            | boolean    | Whether the action should be displayed as an outlined button |
| loading            | boolean    | Whether a spinner should be displayed                        |

IconSource = React.SFC<React.SVGProps<SVGSVGElement>> | 'placeholder' | string;

## Usage

Component will trigger a modal at local route of `/embedded_modal`, and then use message passing to link it to the embedded app and deploy a portal to render react content from `children` within it.

#### Within App

Supply react contents as children:

```
<EmbeddedModal open>
  <div>
    <p>This is some react components</p>
    <CustomComponent />
  </div>
</EmbeddedModal>
```

#### Within /embedded_modal route

Dispatch message to `EmbeddedModal` component to create portal:

```
document.addEventListener('DOMContentLoaded', notifyModalFrameMounted);
```

---

## Best practices

- Modal is configured to deploy at `/embedded_modal`, but can be adjusted via `src` prop
- Modal wraps contents within polaris Card section by default, can be blocked via `sectioned` prop
- Modal height can be configured via `setupModalAutoSizing` method from `app-bridge-utils` (from within `/embedded_modal` window)

---
