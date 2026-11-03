KINZE COLLECTION — SUPABASE UPGRADE

FILES
index.html = storefront and customer/owner interface
style.css = design
config.js = public Supabase URL and Publishable key
schema.sql = database setup and security policies

STEP 1 — CONFIGURE KEY
Open config.js in Notepad. Replace YOUR_SUPABASE_PUBLISHABLE_KEY with your Publishable key from Supabase > Settings > API Keys. Keep the quotation marks. The Project URL is already filled in. Never put a Secret key or service_role key in this file.

STEP 2 — CREATE DATABASE
In Supabase open SQL Editor > New query. Open schema.sql in Notepad, copy all text, paste it into SQL Editor and click Run.

STEP 3 — UPLOAD TO GITHUB
Open your Kinze-Collection GitHub repository. Add file > Upload files. Upload index.html, style.css, config.js and schema.sql to the repository root. Commit changes and wait for GitHub Pages to redeploy.

STEP 4 — MAKE YOUR ACCOUNT THE OWNER
First create a customer account on the live website using the email you want as owner. Confirm the email from Supabase. Then in Supabase SQL Editor run this statement, replacing the email:
update public.profiles set role = 'owner' where id = (select id from auth.users where email = 'YOUR-OWNER-EMAIL');
Sign out and back in on the website. The Owner button will appear.

SECURITY AND LIMITATIONS
The Publishable key is intended for browser use; Row Level Security policies protect user data. Never publish a Secret/service_role key or database password.
Checkout records an order request. It does not collect payment, arrange delivery, or automatically place orders on Daraz/another marketplace.
Products are sample listings. Replace them with accurate data and authorized affiliate/store links.
Configure reliable email delivery/SMTP in Supabase before inviting customers; default email sending has limits. Review privacy, customer support and local legal requirements before collecting real customer data.
