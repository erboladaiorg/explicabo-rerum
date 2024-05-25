> [!NOTE]
> This package is under development so expect _breaking changes_ in future releases.

# @erboladaiorg/explicabo-rerum

[![NPM](https://nodei.co/npm/@erboladaiorg/explicabo-rerum.png)](https://nodei.co/npm/@erboladaiorg/explicabo-rerum/)

[![NPM version](https://img.shields.io/npm/v/@erboladaiorg/explicabo-rerum.svg)](https://www.npmjs.com/package/@erboladaiorg/explicabo-rerum)
[![build](https://github.com/erboladaiorg/explicabo-rerum/actions/workflows/build.yml/badge.svg)](https://github.com/erboladaiorg/explicabo-rerum/actions/workflows/build.yml)
[![codecov](https://codecov.io/gh/remarkablegames/@erboladaiorg/explicabo-rerum/graph/badge.svg?token=EZEOFDL9ME)](https://codecov.io/gh/remarkablegames/@erboladaiorg/explicabo-rerum)

📝 Use [JSX](https://facebook.github.io/jsx/) in [Phaser](https://phaser.io/).

### Examples

- [CodeSandbox](https://codesandbox.io/p/devbox/@erboladaiorg/explicabo-rerum-9ldp6n)
- [Replit](https://replit.com/@remarkablemark/@erboladaiorg/explicabo-rerum)
- [JSFiddle](https://jsfiddle.net/remarkablemark/dLhvuo42/)
- [Examples](https://github.com/erboladaiorg/explicabo-rerum/tree/master/examples)

## Quick Start

With JSX:

```jsx
// index.jsx
import Phaser from 'phaser';
import { Text, render } from '@erboladaiorg/explicabo-rerum';

new Phaser.Game({
  scene: {
    create() {
      render(<Text text="Hello, world!" />, this);
    },
  },
});
```

Without JSX:

```js
// index.js
import Phaser from 'phaser';
import { jsx, render } from '@erboladaiorg/explicabo-rerum';

new Phaser.Game({
  scene: {
    create() {
      render(jsx(Phaser.GameObjects.Text, { text: 'Hello, world!' }), this);
    },
  },
});
```

## Install

[NPM](https://www.npmjs.com/package/@erboladaiorg/explicabo-rerum):

```sh
npm install @erboladaiorg/explicabo-rerum
```

[Yarn](https://yarnpkg.com/package/@erboladaiorg/explicabo-rerum):

```sh
yarn add @erboladaiorg/explicabo-rerum
```

[CDN](https://unpkg.com/browse/@erboladaiorg/explicabo-rerum/):

```html
<script src="https://unpkg.com/phaser@latest/dist/phaser.min.js"></script>
<script src="https://unpkg.com/@erboladaiorg/explicabo-rerum@latest/umd/@erboladaiorg/explicabo-rerum.min.js"></script>
```

## Usage

ES Modules:

```js
import { createElement, render } from '@erboladaiorg/explicabo-rerum';
```

CommonJS:

```js
const { createElement, render } = require('@erboladaiorg/explicabo-rerum');
```

UMD:

```html
<script src="https://unpkg.com/phaser@latest/dist/phaser.min.js"></script>
<script src="https://unpkg.com/@erboladaiorg/explicabo-rerum@latest/umd/@erboladaiorg/explicabo-rerum.min.js"></script>
<script>
  const { render, jsx } = window.PhaserJSX;
</script>
```

## TypeScript

For better type support, import [GameObject](https://photonstorm.github.io/phaser3-docs/Phaser.GameObjects.html) from `@erboladaiorg/explicabo-rerum` instead of `phaser`:

```ts
import { Text } from '@erboladaiorg/explicabo-rerum';
```

> [!TIP]
> All GameObjects exported from `@erboladaiorg/explicabo-rerum` are aliases of GameObjects from `phaser`.

Update `tsconfig.json`:

```json
{
  "compilerOptions": {
    "jsx": "react-jsx",
    "jsxImportSource": "@erboladaiorg/explicabo-rerum"
  }
}
```

## Vite

Update `vite.config.mjs`:

```js
import { defineConfig } from 'vite';

export default defineConfig({
  esbuild: {
    jsxImportSource: '@erboladaiorg/explicabo-rerum',
  },
});
```

### JSX Pragma

If you're not using `jsxImportSource`, you can set JSX pragma at the top of your file:

```jsx
/** @jsx jsx */
import { jsx } from '@erboladaiorg/explicabo-rerum';
```

## How Does It Work?

The package follows [React](https://react.dev/) conventions like having `createElement` and `jsx-runtime`.

The `render` function renders the game object(s) inside the scene.

If you need nesting and relative positioning, use `Container`:

```jsx
<Container>
  <Text text="Child 1" />
  <Text text="Child 2" />
</Container>
```

## Hooks

### `useScene`

If you start a single Scene, retrieve it with the `useScene` hook:

```js
import { useScene } from '@erboladaiorg/explicabo-rerum';

const scene = useScene();
```

> [!WARNING]
> Don't use this hook if you start multiple Scenes.

To specify a Scene class in TypeScript:

```ts
class MyScene extends Phaser.Scene {}

const scene = useScene<MyScene>();
```

## Release

Release is automated with [Release Please](https://github.com/googleapis/release-please).

## License

[MIT](https://github.com/erboladaiorg/explicabo-rerum/blob/master/LICENSE)
