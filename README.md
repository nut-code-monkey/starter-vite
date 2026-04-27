<p align="center">
  <a href="https://elementary.codes">
    <img src="https://elementary-swift.github.io/assets/elementary-logo.svg" width="125px" alt="Elementary Logo">
  </a>
</p>

# Minimal Vite Starter for ElementaryUI in Dev Container

A starter template for building web applications with [ElementaryUI](https://github.com/elementary-swift/elementary-ui) powered by [Vite](https://vite.dev/).

Click **Use this template** on GitHub or check the [docs](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template) about using templates.

You can use [degit](https://github.com/Rich-Harris/degit) to scaffold a local project.
```sh
npx degit elementary-swift/starter-vite my-swift-web-app
```

<p align="center">
  <img src="https://elementary-swift.github.io/assets/vite-starter-split-screen.gif" alt="Elementary Demo Split Screen">
</p>

## Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) or [OrbStack](https://orbstack.dev) (much faster for MacOS) and the [Dev Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension for [VS Code](https://code.visualstudio.com).

## Getting Started

- Open project folder with VS Code
- Press F1 and type "Dev Containers: Reopen in Container
- Wait until container will build itself (first it can take a time)

All tools and dependencies will be installed inside [Dev Container](https://code.visualstudio.com/docs/devcontainers/containers) (swift 6.3.1, Swift WebAssembly SDK, Node.js, wasm-opt, npm)

## Develop

From VS Code terminal start development server with hot reload:
```sh
npm run dev
```

Runs an initial debug build of the WebAssembly app in the browser. Swift files are watched and trigger an instant rebuild/reload on save.

## Deploying

Build in release and bundle for deployment:
```sh
npm run build
```

Preview the built web app locally:
```sh
npm run preview
```

## Configuration

The template comes with a [Vite config](vite.config.ts) that uses *Embedded Swift* for release builds.

```ts
// vite.config.ts
import { defineConfig } from "vite";
import swiftWasm from "@elementary-swift/vite-plugin-swift-wasm";

export default defineConfig({
  plugins: [
    swiftWasm({
      useEmbeddedSDK: true,
    }),
  ],
});
```

For all configuration options, visit the plugin's homepage: [vite-plugin-swift-wasm](https://github.com/elementary-swift/vite-plugin-swift-wasm).

## License

[0BSD License](LICENSE) - use it freely with no attribution required.
