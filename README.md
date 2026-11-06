# Lavender Lane Boutique — beginner setup

This starter website uses plain HTML, CSS and JavaScript. It includes the uploaded Butter Yellow + Lavender Anarkali photo.

## 1. Open it in VS Code
1. Extract `lavender_lane_boutique.zip` on your computer.
2. Open VS Code.
3. Choose **File → Open Folder** and select the extracted `lavender_lane_boutique` folder.
4. In VS Code, open `index.html`.
5. To preview it, install the **Live Server** extension (Extensions icon → search `Live Server` → Install).
6. Right-click `index.html` → **Open with Live Server**.

The website design will work locally. The enquiry form will only save data after Supabase is configured below.

## 2. Create the Supabase database
1. Create a project at https://supabase.com/ and sign in.
2. In your project, open **SQL Editor → New query**.
3. Copy all the SQL from `supabase_setup.sql`, paste it there, and click **Run**.
4. Open **Project Settings → API** (or **Data API**, depending on the dashboard version).
5. Copy the **Project URL** and the **publishable/anon key**. Never use a `service_role` or secret key in a website.
6. In `index.html`, find `SUPABASE_URL` and `SUPABASE_ANON_KEY`, and replace the two placeholder strings with your own values.
7. Save and refresh the website. Submit a test enquiry.
8. In Supabase, open **Table Editor → enquiries** to see the submitted enquiry records.

The SQL enables Row Level Security and permits anonymous visitors to INSERT enquiries only. It does not permit public visitors to read the table. The boutique owner can review enquiries by signing into the Supabase dashboard. Do not share the Supabase dashboard login with customers.

## 3. Upload the project to GitHub
1. Create/sign in to GitHub at https://github.com/.
2. Create a **private** repository, for example `lavender-lane-boutique`.
3. In VS Code, open the Source Control icon on the left.
4. Click **Initialize Repository**.
5. Stage the files, write a commit message such as `Create boutique website`, and commit.
6. Choose **Publish Branch** / **Publish to GitHub**, sign in if asked, and select the private repository you created.

Do not upload passwords, secret keys, or Supabase service-role keys. The website uses only the public anon/publishable key, protected by database Row Level Security.

## 4. Deploy on Vercel
1. Sign in at https://vercel.com/ using GitHub.
2. Choose **Add New → Project**.
3. Import the `lavender-lane-boutique` GitHub repository.
4. For this plain HTML project, no framework preset or build command is needed. Keep the root directory as `./`.
5. Click **Deploy**.
6. Vercel will provide a live website URL. Future pushes to the connected GitHub branch will trigger a new deployment.

## Important before using it for a real boutique
- Replace the sample brand name and text with the boutique owner's approved details.
- Add only real products and photos that the boutique has permission to use.
- Test the form and database before publishing it for customers.
- Add a privacy notice and a real contact method before collecting customer details.
- This starter does not include customer accounts, online payments, inventory, or an admin dashboard. Enquiries are reviewed in the Supabase dashboard.
