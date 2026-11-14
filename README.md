# Commission Studio

Dark Studio workspace for managing a single artist's commission queue, progress, finance notes, and usage permissions.

## Repository status

This repository originally contained a basic Google Sheets display page. The `feat/commission-studio-foundation` branch establishes the next implementation step without overwriting the original `main` branch.

- `index.html`: application entry point (foundation UI)
- `supabase/schema.sql`: owner-scoped database table and row-level security policies
- `.env.example`: frontend environment variable names only

## Data privacy

Customer names, contact handles, notes, and payment details are private. Do not commit the source spreadsheet, customer CSV exports, credentials, or Supabase service-role keys to this repository. Import the private CSV directly into the private Supabase project after creating the owner account.

## Supabase setup

1. Create a Supabase project.
2. In Authentication settings, disable public sign-ups; create only the owner's account.
3. Run `supabase/schema.sql` in the SQL Editor.
4. Add the project URL and anon/publishable key to your deployment environment as `VITE_SUPABASE_URL` and `VITE_SUPABASE_ANON_KEY`.
5. Never put the `service_role` key in browser code.

## Current limitations

The foundation UI is a front-end starting point. Supabase authentication, live database CRUD, CSV import, and deployment are not considered active until those integrations are implemented and tested. Local browser data is not a substitute for cloud sync.
