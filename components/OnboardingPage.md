---
name: OnboardingPage
---

# Onboarding page

Onboarding is a sequence of steps a merchant needs to complete to set up the channel. This process is crucial to a merchant's success, so make sure you present channel requirements and other relevant information up-front.

---

## Props

| Name       | Type                      | Description                                    | Required |
| ---------- | ------------------------- | ---------------------------------------------- | -------- |
| title      | string                    | Page title, in large type                      | Yes      |
| subtitle   | string                    | Page subtitle, in subdued type below title     |          |
| children   | ReactNode[]               | The contents of the page                       | Yes      |
| action     | DisableableLoadableAction | Call to action, rendered as a primary button   | Yes      |
| breadcrumb | BreadcrumbAction          | Navigation link to return to the previous page | Yes      |
| footer     | ReactNode                 | The content displayed in the footer help       |          |

BreadcrumbAction = LinkAction | CallbackAction

### DisableableLoadableAction

| Name               | Type       | Description                                     |
| ------------------ | ---------- | ----------------------------------------------- |
| id                 | string     | A unique identifier for the action              |
| content            | string     | Content the action displays                     |
| accessibilityLabel | string     | Visually hidden text for screen readers         |
| url                | string     | A destination to link to                        |
| external           | boolean    | Forces url to open in a new tab                 |
| onAction           | () => void | Callback when an action takes place             |
| onMouseEnter       | () => void | Callback when mouse enter                       |
| onTouchStart       | () => void | Callback when element is touched                |
| disabled           | boolean    | Whether or not the action is disabled           |
| loading            | boolean    | Whether or not a spinner is displayed in action |

### LinkAction

| Name               | Type   | Description                             | Required |
| ------------------ | ------ | --------------------------------------- | -------- |
| id                 | string | A unique identifier for the action      |          |
| content            | string | Content the action displays             |          |
| accessibilityLabel | string | Visually hidden text for screen readers |          |
| url                | string | A destination to link to                | Yes      |

### CallbackAction

| Name               | Type       | Description                             | Required |
| ------------------ | ---------- | --------------------------------------- | -------- |
| id                 | string     | A unique identifier for the action      |          |
| content            | string     | Content the action displays             |          |
| accessibilityLabel | string     | Visually hidden text for screen readers |          |
| onAction           | () => void | Callback when an action takes place     | Yes      |

---

## Best practices

The onboarding page component should:

- Always provide a title for the page header
- Children should consist of 1 or more `OnboardingCard` components
  - Steps that have been completed should use completed onboarding cards
  - The current step should use an active onboarding card
  - Upcoming steps should use disabled onboarding cards
- Use a breadcrumb to provide a method for merchants to navigate to the previous page
- The action should act as the submit button for the onboarding flow
  - It should be disabled until the merchant has completed all steps in the onboarding flow
  - It can have a loading state while the onboarding form is being submitted
- Use the footer to direct merchants to help documentation related to the channel

### Onboarding steps

- Try to minimize the number of steps in the process by automating and pre-filling information.
- Settings that are shared between multiple features should only be set up once, such as global (main) accounts.
- Use the slow reveal for the steps: show a list of all steps with the first step active. This technique works as a progress bar and allows merchants to see how much is left.
- Ensure merchants are able to use your channel by displaying the requirements early on.
- Specify clearly when a merchant needs to navigate away from Shopify to your platform to complete a task.
- Each onboarding step should have a clear call to action that a merchant clicks to indicate they have completed the step. This should save the information for that step as well as the merchant's progress. Merchants returning to the onboarding flow should return to where they left off, and not have to repeat previously completed onboarding steps.
  - If an external account need to be re-connected, the corresponding step should be active and all future steps disabled. The merchant should be returned to their previously active step once the account has be connected.

---

## Examples

### Basic onboarding page

```jsx
<OnboardingPage
  title="Set up Mockingbird Shopping"
  action={{
    content: 'Finish setup',
  }}
  breadcrumb={{
    url: '/',
    content: 'Back to overview',
  }}
>
  <OnboardingCard id="step-1" title="Step 1" state="completed" sectioned>
    <div>step 1 content</div>
  </OnboardingCard>
  <OnboardingCard id="step-2" title="Step 2" state="completed" sectioned>
    <div>step 2 content</div>
  </OnboardingCard>
</OnboardingPage>
```

### Onboarding page with subtitle

```jsx
<OnboardingPage
  title="Set up Mockingbird Shopping"
  subtitle="To start selling your products on Mockingbird please finish the setup process."
  action={{
    content: 'Finish setup',
  }}
  breadcrumb={{
    url: '/',
    content: 'Back to overview',
  }}
>
  <OnboardingCard id="step-1" title="Step 1" state="completed" sectioned>
    <div>step 1 content</div>
  </OnboardingCard>
  <OnboardingCard id="step-2" title="Step 2" state="completed" sectioned>
    <div>step 2 content</div>
  </OnboardingCard>
</OnboardingPage>
```

### Onboarding page with footer

```jsx
<OnboardingPage
  title="Set up Mockingbird Shopping"
  action={{
    content: 'Finish setup',
  }}
  breadcrumb={{
    url: '/',
    content: 'Back to overview',
  }}
  footer="Learn more about the Mockingbird channel"
>
  <OnboardingCard id="step-1" title="Step 1" state="completed" sectioned>
    <div>step 1 content</div>
  </OnboardingCard>
  <OnboardingCard id="step-2" title="Step 2" state="completed" sectioned>
    <div>step 2 content</div>
  </OnboardingCard>
</OnboardingPage>
```

### Onboarding page with a disabled action

```jsx
<OnboardingPage
  title="Set up Mockingbird Shopping"
  action={{
    content: 'Finish setup',
    disabled: true,
  }}
  breadcrumb={{
    url: '/',
    content: 'Back to overview',
  }}
  footer="Learn more about the Mockingbird channel"
>
  <OnboardingCard id="step-1" title="Step 1" state="completed" sectioned>
    <div>step 1 content</div>
  </OnboardingCard>
  <OnboardingCard id="step-2" title="Step 2" state="completed" sectioned>
    <div>step 2 content</div>
  </OnboardingCard>
</OnboardingPage>
```

### Onboarding page with a loading action

```jsx
<OnboardingPage
  title="Set up Mockingbird Shopping"
  action={{
    content: 'Finish setup',
    loading: true,
  }}
  breadcrumb={{
    url: '/',
    content: 'Back to overview',
  }}
  footer="Learn more about the Mockingbird channel"
>
  <OnboardingCard id="step-1" title="Step 1" state="completed" sectioned>
    <div>step 1 content</div>
  </OnboardingCard>
  <OnboardingCard id="step-2" title="Step 2" state="completed" sectioned>
    <div>step 2 content</div>
  </OnboardingCard>
</OnboardingPage>
```

## Accessibility

This component wraps the page children in an ordered list (`ol`) and wraps each child node in a list item (`li`). This is used to convey the number of steps and progress to merchants going through onboarding using a screen reader.

The breadcrumb prop accepts a `content` property which can be used to provide merchants with more context about where this button will take them (i.e. 'Back to overview').
