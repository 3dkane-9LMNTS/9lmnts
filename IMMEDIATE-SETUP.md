# 🚀 IMMEDIATE SETUP: N8N + PayPal Integration

## ⚡ Do This Right Now (15 minutes)

### 1. PayPal Developer Setup (5 minutes)

1. **Go to**: https://developer.paypal.com
2. **Log in** with your business account (9lmntstudio@gmail.com)
3. **Create App**:
   - Click "My Apps & Credentials" → "Create App"
   - App name: "9LMNTS AI Services"
   - Select: "Merchant"
   - Click "Create App"
4. **Copy Credentials**:
   - Client ID: `_________________________`
   - Client Secret: `_________________________`
   - Webhook ID: `_________________________`

### 2. N8N Credentials Setup (5 minutes)

In your n8n dashboard (https://loax9lmnts.app.n8n.cloud):

#### PayPal Credential:
- **Credentials** → **Add Credential** → **PayPal**
- Environment: **Sandbox** (for testing)
- Client ID: [Paste from above]
- Client Secret: [Paste from above]
- **Save**

#### GitHub Credential:
- Go to: https://github.com/settings/tokens
- **Generate new token** → **Classic**
- Name: "n8n-ai-services"
- Permissions: ✅ `repo`, ✅ `admin:org`, ✅ `workflow`
- Copy token: `_________________________`
- In n8n: **Add Credential** → **GitHub** → Paste token

#### Netlify Credential:
- Go to: https://app.netlify.com/account/applications
- **Create new access token**
- Name: "n8n-integration"
- Permissions: **Full access**
- Copy token: `_________________________`
- In n8n: **Add Credential** → **HTTP Header Auth**
- Name: `Authorization`
- Value: `Bearer [paste token]`

#### Gmail Credential:
- Go to: https://myaccount.google.com/apppasswords
- Generate app password for n8n
- Copy: `_________________________`
- In n8n: **Add Credential** → **Gmail** → Paste password

### 3. Import Workflow (3 minutes)

1. In n8n: **Workflows** → **Import from file**
2. Select: `n8n-paypal-workflow.json`
3. Click **Import**
4. **Save** the workflow
5. **Test** the webhook: Copy the webhook URL

### 4. Test the Flow (2 minutes)

1. **Start your dev server**:
   ```bash
   cd "c:\Users\me\OneDrive\Documents\9LMNTS Studio"
   npm run dev
   ```

2. **Navigate to**: http://localhost:5173/ai-services

3. **Click**: "Get Started" on any service

4. **Pay**: $1 test payment in PayPal Sandbox

5. **Check**: n8n workflow execution

## 🔧 Webhook URL

Your PayPal IPN webhook URL is:
```
https://loax9lmnts.app.n8n.cloud/webhook/paypal-ipn
```

This is already configured in your AI Services page.

## 📊 Expected Flow

1. **Client clicks** "Get Started" → PayPal opens
2. **Client pays** $998.50 deposit → PayPal sends IPN
3. **n8n receives** IPN → Verifies payment
4. **Creates GitHub repo** from template
5. **Deploys to Netlify** automatically
6. **Sends email** to client with credentials
7. **Saves to database** for tracking

## 🎯 Success Metrics

- ✅ Payment received in PayPal
- ✅ n8n workflow triggers
- ✅ GitHub repository created
- ✅ Netlify site deployed
- ✅ Client gets welcome email

## 🚨 Troubleshooting

### PayPal IPN Not Working
- Check webhook URL in PayPal business settings
- Verify n8n webhook is active
- Ensure PayPal app is in Sandbox mode

### GitHub Repo Not Created
- Check Personal Access Token has `repo` scope
- Verify GitHub username in workflow
- Check rate limits

### Netlify Deployment Failed
- Verify Netlify API token
- Check repository name format
- Ensure build configuration exists

## 📞 Quick Help

If stuck:
1. Check n8n execution history
2. Verify all credentials are correct
3. Test with $1 payment first
4. Check browser console for errors

## 🎉 Ready to Launch

Once all 4 credentials are set up and the test payment works:

1. **Switch PayPal to Live mode**
2. **Update pricing** if needed
3. **Launch** on social media
4. **Monitor** first sales

---

**Goal**: $5,000 by Friday
**Timeline**: Setup tonight, launch tomorrow
**Next**: Test complete flow now!
