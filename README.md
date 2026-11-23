# Professor Dr. Hanan Lab CMS

An academic profile and laboratory website built with Astro and EmDash. This is the first site on a reusable CMS foundation intended for professor websites with different frontend designs.

## Project status

- First site: Professor Dr. Md. Abdul Hannan, Department of Biochemistry and Molecular Biology, Bangladesh Agricultural University.
- The profile and five research interests come from the supplied Google Scholar profile.
- Google Scholar: https://scholar.google.com/citations?hl=en&user=-hsEFR0AAAAJ
- No biography, email address, publication records, projects, or lab members are invented; add verified details through the CMS.

## Requirements

- Node.js 22.23.4 or newer. The current build was verified with Node.js 22.23.5.
- npm
- Git

## Run locally

1. Install dependencies:

       npm ci

2. Create a local environment file:

       cp .env.example .env
       openssl rand -hex 32

3. Copy the generated 64-character value into EMDASH_ENCRYPTION_KEY in .env. Keep .env private; use a different key for each environment.

4. Start the development server:

       npm run dev

Astro prints the local URL in the terminal. Open the EmDash admin interface from the site’s generated admin route to edit content.

## Commands

- npm run dev — start the Astro development server.
- npm run typecheck — run Astro’s type checks.
- npm run build — build the server-rendered site.
- npm run preview — preview the build locally.
- npm start — run the standalone Node.js server after building.

## CMS content

The EmDash seed file defines these collections:

- Professor Profiles
- Research Areas
- Publications
- Research Projects
- Lab Members
- Lab News

EmDash Starter’s Pages and Posts collections are also available. The Hanan profile and research-area entries seed the first site; publications, projects, team members, and news should be added after their details are verified.

The homepage reads the professor profile and research areas from EmDash. It links to the supplied Scholar page for publications and citation information.

## Reuse for other professors

Reuse the CMS collections and admin foundation, then give each professor a frontend theme that matches their design choice. The current implementation assumes one reusable codebase and schema with isolated content per professor deployment. It is not yet a multi-tenant hosting setup; record the tenant and deployment decision before onboarding another professor.

## Storage and deployment

The starter is configured for a standalone Node.js server, SQLite database at data.db, and local media under uploads/. These local paths are suitable for development and must be persisted and backed up if used in a deployment. Before production, choose the database and media storage strategy, configure durable backups, and isolate each professor’s admin access and content. Do not deploy the same local SQLite file on ephemeral storage.

## Environment and generated files

Copy .env.example to .env and generate a unique key for each environment. Never commit .env or share its value. The repository ignores .env, local databases, uploads, build output, and node_modules; .env.example is safe to commit because it contains no secret.
