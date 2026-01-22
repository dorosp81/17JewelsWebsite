# 17 Jewels Website

Marketing website and auth pages for the 17 Jewels pocket watch collection app.

## Pages

- `/` - Landing page
- `/confirmed` - Email confirmation success page
- `/reset-password` - Password reset page (functional with Supabase)
- `/privacy` - Privacy Policy
- `/terms` - Terms of Service

## Setup

### 1. Add Images

Create an `images` folder and add:
- `logo.png` - Your gear logo (use SimpleLogoNoBackground.png)
- `favicon.png` - Small favicon version
- `apple-touch-icon.png` - For iOS bookmarks (180x180)
- `app-screenshot.png` - Screenshot of your app for the hero section
- `og-image.png` - Open Graph image for social sharing (1200x630)

### 2. Update Supabase Key

In `reset-password.html`, replace `YOUR_SUPABASE_ANON_KEY` with your actual Supabase anon key:

```javascript
const SUPABASE_ANON_KEY = 'your-actual-anon-key-here';
```

You can find this in Supabase Dashboard → Project Settings → API → `anon` `public` key.

### 3. Update App Store Link

In `index.html`, update the App Store button link once your app is live:

```html
<a href="https://apps.apple.com/app/17-jewels/id123456789" class="app-store-btn">
```

## Deployment to Vercel

### Option A: Vercel CLI

1. Install Vercel CLI: `npm i -g vercel`
2. Run: `vercel`
3. Follow prompts to deploy

### Option B: GitHub + Vercel

1. Push this folder to a GitHub repository
2. Go to [vercel.com](https://vercel.com)
3. Import the repository
4. Deploy

### Option C: Drag & Drop

1. Go to [vercel.com](https://vercel.com)
2. Drag this entire folder to the deploy area
3. Done!

## Connect Custom Domain

1. In Vercel dashboard, go to your project → Settings → Domains
2. Add `17jewels.app`
3. Update your domain's DNS:
   - Add an A record pointing to `76.76.21.21`
   - Or add a CNAME record pointing to `cname.vercel-dns.com`

## Update Supabase Site URL

After deploying, update your Supabase URL Configuration:

1. Go to Supabase Dashboard → Authentication → URL Configuration
2. Set Site URL to: `https://17jewels.app`
3. Add Redirect URL: `https://17jewels.app/reset-password`
4. Add Redirect URL: `pocketwatchapp://**`

## Update Email Templates (Optional)

In Supabase → Authentication → Email Templates:

### Confirm Sign Up
Change the link to redirect to your confirmed page:
```html
<a href="{{ .SiteURL }}/confirmed">Confirm Your Email</a>
```

### Reset Password  
The link will automatically use your Site URL and go to `/reset-password` with the token.

---

Made with ⌚ for 17 Jewels
