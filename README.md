# Mock Storybook

Record & mock your stories with
<abbr title="HTTP Archive format">[HAR][har]</abbr> files.

## Installation

```shell
pnpm add mock-storybook --dev
```

```js
// .storybook/preview.js
export const loaders = withMocks({})([
  ...
])
```

````

Then, in your story:

```js
Story.parameters = {
  mock: {
    har: require('./path/to.har'),
    handlers: [

    ]
  }
}
````

## Local Workflow

1. Automate your story with a `.play()` function via [Interactions][interactions].
1. Capture a `.har` file:

   ### Manually

   See [How to get a HAR capture](https://toolbox.googleapps.com/apps/har_analyzer/)

   ### Automatically

   1. Setup [`test-storybook`][test-storybook]
   1. Run `test-storybook`
   1. TODO – Automatically capture `.har` relative to story?

[har]: https://en.wikipedia.org/wiki/HAR_(file_format)
[interactions]: https://storybook.js.org/addons/@storybook/addon-interactions
[test-storybook]: https://storybook.js.org/addons/@storybook/testing-react
