# Tentang Proyek
JAMStack dengan menggunakan [Supabase](https://supabase.io) sebagai backend, dan [Sveltekit](https://kit.svelte.dev) sebagai framework frontend. Framework CSS yang digunakan adalah [tailwind](https://tailwindcss.com).
#### Susunan proyek
Proses pengembangan dilakukan dalam direktori 'src'
```bash
├──  src
│  ├── app.html
│  ├── lib
│  │  ├── atoms
│  │  │  └── komponen-komponen kecil (tombol, link, dsb)
│  │  ├── comps
│  │  │  └── Komponen-komponen web lebih lengkap (form, navbar, menu, dsb)
│  │  └── db.ts // konektor supabase
│  └── routes
│     ├── __layout.svelte // layout root
│     ├── index.svelte // halaman root ("/")
│     └── signup // halaman 'nama folder'
│        └── index.svelte // komponen halaman
├── static // file-file statis
│  └── favicon.png
│   // pengaturan modul-modul dalam proyek
├── svelte.config.js
├── tailwind.config.cjs
└── tsconfig.json
```
Dokumentasi penting:
- [sveltekit](https://kit.svelte.dev/docs) 
- [svelte](https://svelte.dev/docs)
- [tailwind](https://tailwindcss.com/docs)

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
# npm install
npm i
# mulai server
npm run dev
# atau untuk otomatis buka browser
npm run dev -- --open
```

## Building

Before creating a production version of your app, install an [adapter](https://kit.svelte.dev/docs#adapters) for your target environment. Then:

```bash
npm run build
```

> You can preview the built app with `npm run preview`, regardless of whether you installed an adapter. This should _not_ be used to serve your app in production.
