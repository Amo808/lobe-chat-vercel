# Vercel Deployment Guide

## Quick Steps

1. **Fork Repository**
   - Fork this repository to your GitHub account

2. **Create Vercel Project**
   - Go to <https://vercel.com/dashboard>
   - Click "New Project"
   - Import your forked repository

3. **Set Environment Variables**
   - Go to project settings → Environment Variables
   - Copy from `.env.example` and set these required variables:

   ```
   NEXT_PUBLIC_SERVICE_MODE=server
   NODE_OPTIONS=--max-old-space-size=4096
   NEXT_TELEMETRY_DISABLED=1
   SKIP_ENV_VALIDATION=1
   NEXTAUTH_SECRET=your-random-secret-key
   NEXTAUTH_URL=https://your-app.vercel.app
   OPENAI_API_KEY=your-openai-key
   ```

4. **Deploy**
   - Vercel will automatically build and deploy
   - Your app will be available at `https://your-app.vercel.app`

## Configuration Files

- ✅ `vercel.json` - Optimized build configuration
- ✅ `.npmrc` - Stable npm registry settings
- ✅ `.vercelignore` - Excludes unnecessary files
- ✅ `.env.production` - Production defaults
- ✅ `.env.example` - Environment variable template

## Troubleshooting

### Build Errors

- Ensure `NODE_OPTIONS=--max-old-space-size=4096` is set
- Check all required environment variables are configured

### Network Timeout Issues

- The `.npmrc` file includes retry logic for stability
- Build may take 2-3 minutes on first deploy

### Function Timeout

- API routes have 60-second timeout (Vercel Pro required for longer)
- Database queries should be optimized

## Success Indicators

✅ Build completes successfully\
✅ Function deployments show no errors\
✅ App loads at your Vercel URL\
✅ Chat functionality works with your API keys\
✅ No console errors in browser dev tools

## Next Steps

- Configure additional AI providers in environment variables
- Set up database for conversation persistence
- Enable authentication if needed
- Configure custom domain (optional)
