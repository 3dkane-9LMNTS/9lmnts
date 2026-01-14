# 🚀 N8N Integration Setup Guide for 9LMNTS Studio AI Services

## 📋 Quick Setup Checklist

### 1. PayPal Integration
- [ ] Log into PayPal Developer: https://developer.paypal.com/
- [ ] Create new App → Select "Merchant"
- [ ] Get Client ID and Client Secret
- [ ] In n8n: Credentials → Add Credential → PayPal
- [ ] Configure: Sandbox → Live, add credentials
- [ ] Copy Webhook ID for IPN

### 2. GitHub Integration  
- [ ] Go to GitHub Settings → Developer settings → Personal access tokens
- [ ] Generate new token (classic)
- [ ] Permissions: `repo`, `admin:org`, `workflow`
- [ ] In n8n: Credentials → Add Credential → GitHub
- [ ] Add Personal Access Token

### 3. Netlify Integration
- [ ] Log into Netlify → User settings → Applications
- [ ] Create new access token → Full access
- [ ] In n8n: Credentials → Add Credential → HTTP Header Auth
- [ ] Name: Authorization, Value: Bearer YOUR_NETLIFY_TOKEN

### 4. Email Integration (Gmail)
- [ ] Enable 2-factor authentication on Google Account
- [ ] Go to Google Account → Security → App passwords
- [ ] Generate app password for n8n
- [ ] In n8n: Credentials → Add Credential → Gmail
- [ ] Configure with app password

### 5. Supabase Integration
- [ ] Go to Supabase Project → Settings → API
- [ ] Copy Project URL and Service Role Key
- [ ] In n8n: Credentials → Add Credential → Supabase
- [ ] Add URL and Service Role Key

## 🔧 Import the Workflow

1. Open n8n Dashboard
2. Click "Import from file" 
3. Select `n8n-paypal-workflow.json`
4. Update webhook URL in PayPal buttons
5. Test with $1 payment

## 📝 Update PayPal Webhook URL

In `src/components/AiServicesPage.tsx`, update line 107:

```typescript
notify_url: 'https://YOUR_N8N_URL.com/webhook/paypal-ipn'
```

Replace with your actual n8n webhook URL.

## 🎯 Create GitHub Templates

Create these repositories on GitHub:

1. `ai-sales-machine-template`
2. `content-engine-template` 
3. `email-agent-template`

Each should include:
- README.md
- package.json
- src/index.js
- .env.example
- deployment instructions

## ⚡ Test the Complete Flow

1. Start your dev server: `npm run dev`
2. Navigate to AI Services page
3. Click "Get Started" on any service
4. Complete $1 test payment in PayPal Sandbox
5. Check n8n execution history
6. Verify GitHub repo creation
7. Check Netlify deployment
8. Confirm client email sent

## 🔄 Workflow Steps

1. **PayPal IPN Webhook** → Receives payment notification
2. **Verify PayPal IPN** → Confirms payment is legitimate
3. **Filter Completed Payment** → Only processes completed transactions
4. **Create GitHub Repository** → Makes new repo from template
5. **Create Netlify Site** → Deploys repo to Netlify
6. **Save to Supabase** → Records client in database
7. **Email Client** → Sends welcome email with credentials

## 📊 Expected Results

- **Payment Received**: Client pays $998.50 deposit
- **Auto-Repo**: GitHub repo created instantly
- **Auto-Deploy**: Netlify site deployed automatically  
- **Client Notification**: Email sent within 5 minutes
- **Database Record**: Client saved to Supabase

## 🚨 Troubleshooting

### PayPal IPN Not Working
- Check webhook URL is correct
- Verify PayPal IPN settings in business account
- Ensure n8n webhook is active

### GitHub Repo Not Created
- Verify Personal Access Token has `repo` scope
- Check GitHub API rate limits
- Ensure template repository exists

### Netlify Deployment Failed
- Verify Netlify API token
- Check repository has build configuration
- Ensure GitHub repo is public or token has access

### Email Not Sending
- Check Gmail app password
- Verify n8n email credentials
- Check spam folder

## 🎉 Launch Ready Once:

- [ ] All 5 integrations connected in n8n
- [ ] Workflow imported and tested
- [ ] PayPal buttons using correct webhook URL
- [ ] GitHub templates created
- [ ] Test payment completes successfully
- [ ] Client receives welcome email
- [ ] Site deployed to Netlify

## 📈 Next Steps

1. **Scale**: Create more service templates
2. **Automate**: Add Windsurf code generation
3. **Monitor**: Set up analytics and alerts
4. **Market**: Launch to your audience
5. **Support**: Prepare client onboarding flow

---

**Target**: $5,000 by Friday
**Path**: 2x AI Sales Machine ($1,997) + 1x Content Engine ($1,497)
**Timeline**: Complete setup tonight, launch tomorrow morning
