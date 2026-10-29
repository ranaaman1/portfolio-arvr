# Inquiry storage setup

The portfolio now stores contact inquiries in Supabase instead of sending them through the placeholder email form.

## 1. Create the database table

1. Open the Supabase project dashboard.
2. Open **SQL Editor**.
3. Paste the contents of `supabase-schema.sql`.
4. Run the SQL.

The policy allows visitors to submit inquiries but does not allow the public website to read, edit, or delete inquiries.

## 2. Add the public project values

Open `index.html` and confirm these two public values near the bottom:

```js
const SUPABASE_URL = 'https://your-project-id.supabase.co';
const SUPABASE_ANON_KEY = 'sb_publishable_...';
```

Find both values in **Project Settings → API**:

- **Project URL** → `SUPABASE_URL`
- **Publishable key** → `SUPABASE_ANON_KEY`

Only use the public anon/publishable key in the portfolio. Never put a `service_role` key in `index.html`.

## 3. View inquiries

Open **Table Editor → portfolio_inquiries** in Supabase. New submissions will appear there with their timestamp, contact details, subject, message, and source URL.

## 4. Test

Submit the form from the public site. It should show:

> Thanks — your inquiry was received securely.

If the two values are still placeholders, the form intentionally shows a setup error instead of pretending that the inquiry was stored.
