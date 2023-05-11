# Compose Starter: Help Center + Next.js

This is a sample website frontend to help you get started with Compose and
Next.js. You can use this example with Compose's quick start "Simple website" content model for empty
spaces.

## Getting started

### Installing dependencies

```
yarn
```

### Running locally

Copy `.env.example` to `.env` and adapt the environment to your setup:

- `CF_SPACE_ID`: The ID of a Compose compatible space to be used
- `CF_DELIVERY_ACCESS_TOKEN`: A delivery API key for the space
- `CF_PREVIEW_ACCESS_TOKEN`: A preview API key for the space

and then

```
yarn run dev
```

to start the website on `http://localhost:3000`

## Deploy to Vercel

You can use [Vercel](https://vercel.com/) to easily deploy the app by clicking the deploy button below:

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fcontentful%2Fcompose-starter-helpcenter-nextjs&env=CF_SPACE_ID,CF_DELIVERY_ACCESS_TOKEN,CF_PREVIEW_ACCESS_TOKEN&envDescription=Space%20ID%20and%20API%20Keys%20needed%20for%20the%20frontend%20to%20access%20your%20Contentful%20Space&envLink=https%3A%2F%2Fapp.contentful.com%2Fdeeplink%3Flink%3Dapi&project-name=contentful-compose-helpcenter-starter&repo-name=contentful-compose-helpcenter-starter)

For manual deployment, you can following the steps below:

1.  Open your Vercel dashboard and click on "New project".
2.  Click on "Import a Third-Party Git Repository" and enter the url of this repo.
3.  Choose the Vercel scope where you want to deploy the app.
    - For example your personal scope.
4.  Add the 3 environment variables in the project settings:
    - `CF_SPACE_ID`: The ID of a Compose compatible space to be used;
    - `CF_DELIVERY_ACCESS_TOKEN`: A delivery API key for the space;
    - `CF_PREVIEW_ACCESS_TOKEN`: A preview API key for the space.

You are all set! When the deployment run completes, you will see the app at the url generated by Vercel. It can be seen in the overview page of the new project.

## Tech used

- [Next.js 12.x][nextjs]
- [TypeScript 4.x][typescript]
- [Tailwind CSS][tailwind]

## Project structure

```
public/
src/
  ├ components
  ├ lib
  │   ├ translations/
  │   ├ generated-types/
  │   ├ api.ts
  │   └ ... etc
  │
  ├ pages/
  │    ├ [locale]/
  │    │   ├ articles/
  │    │   │    └ [slug].tsx
  │    │   │
  │    │   ├ [slug].tsx
  │    │   └ index.ts
  │    │
  │    ├ ...
  │    └ index.tsx
  │
  └ styles/
next.config.js
...
```

- **src/pages**
  Lists all the pages/routes on the website. See the official Next.js [documentation][pages] about pages for more information.

- **src/components**
  It contains all React components other than Pages. The most important components here, those under `src/components/renderer`, correspond directly to the Content Types we support previewing.

  The `block-renderer.tsx` responsibility is to correctly render a given entry depending on its Content Type.

- **src/lib**

  It contains any code that isn't a component or a Page, notably the fetching and translation logic and Content Types definitions (see below).

## Generating Content Types

We use [cf-content-types-generator][cf-content-types-generator] to keep the Content Types definitions in `src/lib/generated-types` in sync with the space we use.

```shell
# Credentials to be used by cf-content-types-generator (see package.json)
export CF_SPACE_ID=<space-id>
export CF_CMA_TOKEN=<your-cma-token>

# Generate
yarn generate-types
```

## Reach out to us

### You have questions about how to use this repo?

- Reach out to our community forum: [![Contentful Community Forum](https://img.shields.io/badge/-Join%20Community%20Forum-3AB2E6.svg?logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1MiA1OSI+CiAgPHBhdGggZmlsbD0iI0Y4RTQxOCIgZD0iTTE4IDQxYTE2IDE2IDAgMCAxIDAtMjMgNiA2IDAgMCAwLTktOSAyOSAyOSAwIDAgMCAwIDQxIDYgNiAwIDEgMCA5LTkiIG1hc2s9InVybCgjYikiLz4KICA8cGF0aCBmaWxsPSIjNTZBRUQyIiBkPSJNMTggMThhMTYgMTYgMCAwIDEgMjMgMCA2IDYgMCAxIDAgOS05QTI5IDI5IDAgMCAwIDkgOWE2IDYgMCAwIDAgOSA5Ii8+CiAgPHBhdGggZmlsbD0iI0UwNTM0RSIgZD0iTTQxIDQxYTE2IDE2IDAgMCAxLTIzIDAgNiA2IDAgMSAwLTkgOSAyOSAyOSAwIDAgMCA0MSAwIDYgNiAwIDAgMC05LTkiLz4KICA8cGF0aCBmaWxsPSIjMUQ3OEE0IiBkPSJNMTggMThhNiA2IDAgMSAxLTktOSA2IDYgMCAwIDEgOSA5Ii8+CiAgPHBhdGggZmlsbD0iI0JFNDMzQiIgZD0iTTE4IDUwYTYgNiAwIDEgMS05LTkgNiA2IDAgMCAxIDkgOSIvPgo8L3N2Zz4K&maxAge=31557600)][contentful-community]
- Jump into our community slack channel: [![Contentful Community Slack](https://img.shields.io/badge/-Join%20Community%20Slack-2AB27B.svg?logo=slack&maxAge=31557600)][contentful-slack]

### You found a bug or want to improve this repo?

- File an issue here on GitHub: [![File an issue](https://img.shields.io/badge/-Create%20Issue-6cc644.svg?logo=github&maxAge=31557600)][new-issue]. Make sure to remove any credential from your code before sharing it.

### You need to share confidential information or have other questions?

- File a support ticket at our Contentful Customer Support: [![File support ticket](https://img.shields.io/badge/-Submit%20Support%20Ticket-3AB2E6.svg?logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCA1MiA1OSI+CiAgPHBhdGggZmlsbD0iI0Y4RTQxOCIgZD0iTTE4IDQxYTE2IDE2IDAgMCAxIDAtMjMgNiA2IDAgMCAwLTktOSAyOSAyOSAwIDAgMCAwIDQxIDYgNiAwIDEgMCA5LTkiIG1hc2s9InVybCgjYikiLz4KICA8cGF0aCBmaWxsPSIjNTZBRUQyIiBkPSJNMTggMThhMTYgMTYgMCAwIDEgMjMgMCA2IDYgMCAxIDAgOS05QTI5IDI5IDAgMCAwIDkgOWE2IDYgMCAwIDAgOSA5Ii8+CiAgPHBhdGggZmlsbD0iI0UwNTM0RSIgZD0iTTQxIDQxYTE2IDE2IDAgMCAxLTIzIDAgNiA2IDAgMSAwLTkgOSAyOSAyOSAwIDAgMCA0MSAwIDYgNiAwIDAgMC05LTkiLz4KICA8cGF0aCBmaWxsPSIjMUQ3OEE0IiBkPSJNMTggMThhNiA2IDAgMSAxLTktOSA2IDYgMCAwIDEgOSA5Ii8+CiAgPHBhdGggZmlsbD0iI0JFNDMzQiIgZD0iTTE4IDUwYTYgNiAwIDEgMS05LTkgNiA2IDAgMCAxIDkgOSIvPgo8L3N2Zz4K&maxAge=31557600)][contentful-support]

## License

This project is licensed under the MIT license.

[nextjs]: https://nextjs.org/docs/getting-started
[cf-content-types-generator]: https://github.com/contentful-labs/cf-content-types-generator
[tailwind]: https://tailwindcss.com/
[typescript]: https://www.typescriptlang.org/
[pages]: https://nextjs.org/docs/basic-features/pages
[contentful-community]: https://www.contentfulcommunity.com/
[contentful-support]: https://contentful.com/support
[contentful-slack]: https://www.contentful.com/slack/
[new-issue]: https://github.com/contentful/compose-starter-helpcenter-nextjs/issues/new