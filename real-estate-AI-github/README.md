# Bina.az Real Estate Intelligence — Deployment Guide

## Your project folder should contain these files:

```
baku-real-estate/
├── index.html                   ← the web app
├── vercel.json                  ← Vercel configuration
├── bina_az_model_explainer.pptx ← the PowerPoint (copy from real_estate_project)
└── api/
    └── predict.js               ← the secure backend function
```

---

## Step-by-step deployment on Vercel

### Step 1 — Get a free Anthropic API key
1. Go to console.anthropic.com
2. Sign up for a free account
3. Click "API Keys" in the left sidebar
4. Click "Create Key" — copy it and save it somewhere safe
   (it looks like: sk-ant-api03-xxxxxxxxxxxx)

### Step 2 — Create a free Vercel account
1. Go to vercel.com
2. Click "Sign Up" — use your personal Google account
3. You are now on your Vercel dashboard

### Step 3 — Install Vercel CLI (one-time setup)
Open Command Prompt and run:
```
npm install -g vercel
```
If npm is not found, install Node.js first from nodejs.org (choose the LTS version)

### Step 4 — Deploy your project
In Command Prompt, navigate to your project folder:
```
cd C:\Users\Fuad Aliyev\Downloads\baku-real-estate
```
Then run:
```
vercel
```
Follow the prompts:
- "Set up and deploy?" → Y
- "Which scope?" → select your personal account
- "Link to existing project?" → N
- "What's your project's name?" → baku-real-estate (or anything you like)
- "In which directory is your code located?" → ./ (just press Enter)
- All other questions → press Enter to accept defaults

Vercel will deploy and give you a URL like: https://baku-real-estate.vercel.app

### Step 5 — Add your API key (most important step)
This is how you add the key WITHOUT it being visible in your code:

1. Go to vercel.com and open your project dashboard
2. Click "Settings" tab at the top
3. Click "Environment Variables" in the left menu
4. Click "Add New"
5. Name:  ANTHROPIC_API_KEY
   Value: sk-ant-api03-xxxxxxxxxxxx  (paste your key here)
6. Make sure "Production", "Preview", and "Development" are all checked
7. Click "Save"
8. Go back to your project and click "Deployments"
9. Click the three dots next to the latest deployment → "Redeploy"

Your app is now live and the API key is secure!

---

## Your live URL
After deployment you will have a URL like:
https://baku-real-estate.vercel.app

You can share this link with anyone. They can:
- Click "Show me how it works" to see the PPT overview
- Enter property details and get a live AI price estimate
- View the source data table
- Run the scraper to enhance the dataset

---

## Custom domain (optional)
If you want a custom URL like baku-realestate.com:
1. Buy a domain on namecheap.com or godaddy.com (~$10/year)
2. In Vercel project settings → "Domains" → add your domain
3. Follow the DNS instructions Vercel provides

---

## Costs
- Vercel hosting: FREE (free tier is generous for personal projects)
- Anthropic API: Pay per use — each price prediction costs ~$0.001 (less than 0.1 cents)
  At 100 predictions/day that's about $3/month
