# Changelog

All notable changes to `@shopify/channels-ui` will be documented in this file.

---

## 0.3.0 - 2022-03-23

### Breaking changes

- Removed the public sass api. You will no longer be able to import `@shopify/channels-ui/dist/styles/_public-api.scss` into consuming apps.
- The component styles have moved from `dist/styles.css` to `build/esm/styles.css`. Consumers who import styles shall need to update their import path. 

```diff
- import '@shopify/polaris/dist/styles.css';
+ import '@shopify/polaris/build/esm/styles.css';
```

### Dependencies

- Bumped `@shopify/polaris` to `v9.0.0`

## 0.2.0 - 2022-03-03

### Breaking changes

- Bumped min node version to 16.13.0

### Enhancements

- [OnboardingPage] Added optional subtitle under main page title
- [Checklist] Added divider on completed collapsible checklists
- Exported `I18nContext` and `I18n` utilities from the package

### Bug fixes

- [OnboardingInfo] Support strings for the items > content prop 
- [EmbeddedModal] Fixed square corners on footer

### Dependencies

- Bumped `polaris` to `v8.0.0`
- Bumped `react`, `react-dom` to `v17.0.0`
  - Channels-UI has updated its peer dependencies on `react` and `react-dom` to `^16.14.0 || ^17.0.0` to allow for using the [automatic runtime](https://reactjs.org/blog/2020/09/22/introducing-the-new-jsx-transform.html) in a future release. Ensure you are using versions of `react` and `react-dom` that satisfies this version range. Use the package manager of your choice to install a recent version of these packages.
- Bumped `@shopify/app-bridge-react` to `v2.0.7`
- Bumped `@shopify/app-bridge` to `v2.0.7`