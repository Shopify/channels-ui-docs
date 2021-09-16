# Channels UI Library

`@shopify/channels-ui` is a React component library designed to help developers create the best marketplace channel experiences for merchants. This library shares many of the same philosophies as Polaris, and we recommend giving the [style guide](https://polaris.shopify.com/) and [codebase](https://github.com/Shopify/polaris-react) a look if you're building a marketplace channel app.

## Using the React components 

### Installation

Run the following command using [npm](https://www.npmjs.com/): 

```bash
npm install --save @shopify/channels-ui
```

If you prefer [Yarn](https://yarnpkg.com/en/), use the following command instead:

```bash
yarn add @shopify/channels-ui
```

### Usage 

To use the React components you need to wrap your React app in the `ExtendedAppProvider` provided by Channels UI. This also adds the [Polaris App Provider](https://polaris.shopify.com/components/structure/app-provider), and [App Bridge Provider](https://shopify.dev/apps/tools/app-bridge/react-components/provider), so you do not need to add these providers again. Only one `ExtendedAppProvider` is needed for your application.

1. Import Polaris and Channels UI CSS directly into your project:

```jsx
import '@shopify/polaris/dist/styles.css';
import '@shopify/channels-ui/dist/styles.css';
```

2. Include the translations and any Polaris or Channel UI components in your project:

```jsx
import polarisTranslations from '@shopify/polaris/locales/en.json';
import channelsUiTranslations from '@shopify/channels-ui/locales/en.json';
import {ExtendedAppProvider, IntroductionPage} from '@shopify/channels-ui';
import {Card, Button} from '@shopify/polaris';
```

> If your channel supports multiple languages, you can dynamically import translations from the desired locale.

3. Tell React to render the element in the DOM:

```jsx
const appBridgeConfig = {
  apiKey: 'API key from Shopify Partner Dashboard',
  host: 'host from URL search parameter',
  forceRedirect: true,
}

ReactDOM.render(
  <ExtendedAppProvider config={appBridgeConfig} polaris={{i18n: polarisTranslations}} i18n={channelsUiTranslations}>
    <IntroductionPage title="Example channel">
      <Card title="Welcome" sectioned>
        <Button onClick={() => alert('Button clicked!')}>Example button</Button>
      </Card>
    </IntroductionPage>
  </ExtendedAppProvider>,
  document.querySelector('#app'),
);
```

See the [Getting started]("https://github.com/Shopify/channels-ui-docs/blob/main/LICENSE.md") guide for more information on how to build a simple marketplace channel app experience. 
