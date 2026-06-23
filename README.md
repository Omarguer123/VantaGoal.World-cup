# VantaGoal Vercel Fixed

This version fixes the Vercel deployment error:

`The pattern "api/football.js" defined in functions doesn't match any Serverless Functions`

## What was fixed

- Removed the `functions` block from `vercel.json`.
- Kept the serverless API route at `api/football.js`.
- Rewrote the API file with the classic Vercel `req, res` handler.
- The frontend still calls `/api/football`.
- The API key stays in Vercel Environment Variables.

## Correct root structure

When you upload to GitHub, the repository root must contain:

- `index.html`
- `api/football.js`
- `vercel.json`
- `package.json`
- `sitemap.xml`
- `robots.txt`

Do not upload the folder inside another folder like:

`VantaGoal.World-cup/vantagoal_vercel_fixed_dashboard/index.html`

The files must be directly in the root:

`VantaGoal.World-cup/index.html`

## Vercel settings

Framework preset: Other

Build command: leave empty

Output directory: leave empty

Environment variable:

`API_FOOTBALL_KEY`

## Test after deploy

Open:

`https://your-domain.vercel.app/api/football?type=fixtures&date=2026-06-22`

If the API key is correct, you should see JSON from API-Football.

Then open the homepage.


## AdSense verification added

The AdSense code snippet was inserted inside the `<head>` section of the public HTML pages.

Inserted into:
- index.html
- live-scores.html
- groups-standings.html
- schedule-today.html
- watch-guide.html

Also added:
- `ads.txt`

After uploading to GitHub and redeploying on Vercel, return to AdSense and click:
`I've placed the code` → `Verify`
