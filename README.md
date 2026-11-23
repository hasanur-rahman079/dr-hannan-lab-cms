# Professor Dr. Hanan Lab CMS

An EmDash + Astro academic profile and laboratory site, set up as the first deployment of a reusable CMS foundation for professor websites. The CMS schema can be reused across professor sites; each professor can have an independently designed Astro frontend and separate site content.

## First site

The first profile is based on the supplied Google Scholar profile for Professor Dr. Md. Abdul Hannan, Department of Biochemistry and Molecular Biology, Bangladesh Agricultural University. Research areas currently shown: Natural Product Research, Phytomedicine, Network Biology, Marine Biotechnology, and Lifestyle diseases. The homepage links to the supplied Google Scholar profile. Contact details, biography, lab roster, projects, and publications should be added through the EmDash admin when verified source content is available.

## CMS collections

The seed schema defines professor profiles, research areas, publications, research projects, lab members, and lab news, alongside EmDash Starter's pages and posts. These collections are content structures; they do not imply that sample records have been verified or populated.

## Local development

Use Node.js 22.23.5 (EmDash requires Node.js 22.23.4 or newer) and npm. Install with npm install, then run npm run dev. The starter uses local SQLite and local media storage by default; configure production storage and database per deployment before hosting. Never commit .env, data.db, uploads, or node_modules.
