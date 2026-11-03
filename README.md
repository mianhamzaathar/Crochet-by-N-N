# Crochet by N&N

A polished online storefront for handmade crochet flowers, bouquets, bags, plushies, accessories, and thoughtful gifts. Built with React and Vite, the site features an interactive product catalog, shopping cart, wishlist, and WhatsApp ordering experience.

**Live store:** [ayaanabeauty.vercel.app](https://ayaanabeauty.vercel.app/)  
**Repository:** [mianhamzaathar/Crochet-by-N-N](https://github.com/mianhamzaathar/Crochet-by-N-N)

## Highlights

- Responsive storefront with an interactive crochet studio hero.
- Product discovery by category, with product details and image galleries.
- Shopping cart, wishlist, currency display, and order flow.
- WhatsApp contact and ordering integration.
- Optional Supabase-backed catalog and store data.
- Vite production build with route fallback configuration for Vercel.

## Tech stack

- React 19
- Vite 8
- Three.js
- Lucide icons
- Supabase REST API (optional)
- Vercel deployment configuration

## Run locally

Requirements: Node.js 20.19+ or 22.12+ and npm.

```bash
git clone https://github.com/mianhamzaathar/Crochet-by-N-N.git
cd Crochet-by-N-N
npm install
npm run dev
```

Vite prints the local development URL in the terminal.

## Environment variables

The storefront works with its bundled catalog. To connect a Supabase project, create a `.env` file in the project root:

```env
VITE_SUPABASE_URL=https://your-project-id.supabase.co
VITE_SUPABASE_ANON_KEY=your-supabase-anon-key
```

Use a Supabase anon/public key protected by appropriate Row Level Security policies. Never put a Supabase service-role key or other server secret in a `VITE_` variable; Vite exposes these values to the browser. The schema starter is in [`supabase_schema.sql`](supabase_schema.sql).

## Production build

```bash
npm run build
npm run preview
```

The production files are generated in `dist/`. The included [`vercel.json`](vercel.json) supplies the single-page application fallback and cache headers.

## Deploy to Vercel

1. Import `mianhamzaathar/Crochet-by-N-N` in Vercel.
2. Set the framework preset to **Vite** (or let Vercel detect it).
3. Use `npm run build` as the build command and `dist` as the output directory.
4. Add the two Supabase environment variables only if the connected database is being used.
5. Deploy the production branch.

The project can also be deployed with the Vercel CLI after authenticating and linking the project:

```bash
npm i -g vercel
vercel link
vercel --prod
```

## Repository overview

```text
src/
  components/   Storefront sections, product UI, and dialogs
  context/      Cart, wishlist, products, and store state
  data/         Product and category catalog
  lib/          Supabase REST integration
public/assets/  Brand, product, and category assets
supabase_schema.sql
vercel.json
```

## Notes

- Product prices and descriptions in the starter catalog are example store content; confirm current availability and pricing before publishing changes.
- Keep credentials out of source control. `.env` files are ignored by Git.
- Confirm that the configured WhatsApp contact and Supabase policies match the store owner's setup before launch.

## License

No license is currently specified. All rights reserved unless the repository owner adds a license file.
