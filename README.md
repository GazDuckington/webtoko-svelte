# Download Proyek
#### Manual
- Klik tombol hijau ber-label `Code` di sudut kanan repo
- Klik Download ZIP
- Extract File ter-download
#### Git
```bash
git clone https://github.com/RegalOctopus/webtoko-svelte.git
```

# Development Lokal

```bash
# masuk ke direktori proyek
cd webtoko-svelte
# init node
npm i
# mulai server
npm run dev
# atau untuk otomatis buka browser
npm run dev -- --open
```

# create-svelte

Everything you need to build a Svelte project, powered by [`create-svelte`](https://github.com/sveltejs/kit/tree/master/packages/create-svelte);

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npm init svelte@next

# create a new project in my-app
npm init svelte@next my-app
```

> Note: the `@next` is temporary

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

Before creating a production version of your app, install an [adapter](https://kit.svelte.dev/docs#adapters) for your target environment. Then:

```bash
npm run build
```

> You can preview the built app with `npm run preview`, regardless of whether you installed an adapter. This should _not_ be used to serve your app in production.
