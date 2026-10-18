# Mental Models Library

A responsive learning platform for 18 mental-model books, connected to Supabase.

## Deployment
1. GitHub repository: demoaccountdfe545/mental-models-library.
2. GitHub → Settings → Pages → Build and deployment → Deploy from a branch → main → /(root) → Save.
3. Supabase project: qlsroeshnpjmsoewsuvt.
4. The app connects using a public publishable key; server-side secrets are never stored in this repository.
5. Supabase Auth URL Configuration: set Site URL to the GitHub Pages URL, and add that URL to Redirect URLs.
6. Import the private SQL manuscript and quiz seed with Supabase SQL Editor. Do NOT add it to this public repo.
7. Invite/create the owner account in Supabase Auth, then promote just that account to administrator with:
```sql
update public.profiles set role='admin' where email='YOUR_ACTUAL_EMAIL';
```
8. Test sign-in, assigned-book reading, save progress, quizzes, invitation flow and access revocation before selling.
## Security
- RLS restricts chapter access by entitlement.
- Quiz answer keys stay in protected tables; scoring is computed server side.
- Invitation function verifies admin role and uses server-provided Supabase credentials.
- GitHub Pages is public; avoid uploading private content or database secrets.
## Current status
Catalog and schema deployed. Chapters and quiz seed, admin bootstrap and Pages configuration still need completion.
