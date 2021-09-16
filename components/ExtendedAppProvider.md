---
name: ExtendedAppProvider
---

# ExtendedAppProvider

Wrapper provider to initialize Polaris, App Bridge, and Channels-UI translations together.

---

## Props

| Name     | Type                  | Description                                                  | Required |
| -------- | --------------------- | ------------------------------------------------------------ | -------- |
| config   | AppConfig             | Your App Bridge configuration                                | Yes      |
| children | ReactNode             | The contents of your app                                     | Yes      |
| polaris  | PolarisProviderProps  | The props for the Polaris AppProvider                        | Yes      |
| i18n     | TranslationDictionary | A locale object imported from `@shopify/channels-ui/locales` | Yes      |

### AppConfig

| Name          | Type    | Desription                                                                                     | Default | Required |
| ------------- | ------- | ---------------------------------------------------------------------------------------------- | ------- | -------- |
| apiKey        | string  | API key from Shopify Partner Dashboard                                                         |         | Yes      |
| host          | string  | The hostname for the current shop                                                              |         | Yes      |
| forceRedirect | boolean | Use to toggle redirecting to Shopify Admin when the app is not opened inside the Shopify Admin | true    |          |

[Learn more](https://shopify.dev/tools/app-bridge/react-components/provider)

### PolarisProviderProps

| Name          | Type                  | Description                                                        | Required |
| ------------- | --------------------- | ------------------------------------------------------------------ | -------- |
| i18n          | TranslationDictionary | A locale object imported from `@shopify/polaris/locales`           | Yes      |
| linkComponent | ComponentType         | A custom component to use for all links used by Polaris components |          |

[Learn more](https://polaris.shopify.com/components/structure/app-provider)

---

## Best practices

- Use at top level of application as a replacement for app-bridge `Provider` and polaris `AppProvider`
- Forwards supplied provider props for app-bridge (`config`) and polaris (`polaris`)

---

## Usage

```jsx
import {ExtendedAppProvider} from '@shopify/channels-ui';

import polarisTranslations from '@shopify/polaris/locales/en.json';
import channelsUiTranslations from '@shopify/channels-ui/locales/en.json';

function App() {
  return (
    <ExtendedAppProvider
      config={/* App bridge props */}
      polaris={{i18n: polarisTranslations}}
      i18n={channelsUiTranslations}
    >
      {/* App content */}
    </ExtendedAppProvider>
  );
}
```
