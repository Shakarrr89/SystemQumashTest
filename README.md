# Girfan

Personal finance app. Single page (`index.html`) hosted on GitHub Pages, with login and data storage in Supabase.

## Setup

### 1. Supabase database
1. Open **SQL Editor** in your Supabase project.
2. Paste the whole content of `supabase-setup.sql` and click **Run**.

### 2. Supabase login settings
1. Go to **Authentication > Sign In / Providers > Email** and make sure Email is enabled.
2. Turn **off** "Allow new users to sign up" so nobody can create an account themselves.
3. Go to **Authentication > URL Configuration** and set the Site URL to your GitHub Pages address, e.g. `https://YOUR-USERNAME.github.io/YOUR-REPO/`.

### 3. Add users
1. Go to **Authentication > Users > Add user**.
2. Enter the email and a password, and tick **Auto Confirm User**.
3. The user can now sign in on the site with that email and password.

The admin (`shakarkamal15@gmail.com`) gets an **Admin** button that lists all users.

### 4. Publish on GitHub Pages
1. Create a new repository and upload `index.html` (and this README if you like) to the root.
2. Go to **Settings > Pages**, choose branch `main` and folder `/ (root)`, then save.
3. Open the URL GitHub shows.

## Notes
- Each user only sees and changes their own data. The database enforces this.
- The Supabase publishable key in `index.html` is meant to be public. Do not put the secret key in the file.
- Receipt photos are stored in the browser only and do not sync between devices. Everything else syncs.
