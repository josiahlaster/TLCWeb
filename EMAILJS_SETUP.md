# EmailJS Setup Instructions

To complete the email functionality, you need to configure EmailJS:

## Step 1: Create EmailJS Account
1. Go to [https://www.emailjs.com/](https://www.emailjs.com/)
2. Sign up for a free account (200 emails/month)

## Step 2: Add Email Service
1. In the EmailJS dashboard, go to **Email Services**
2. Click **Add New Service**
3. Choose your email provider (Gmail, Outlook, etc.)
4. Follow the instructions to connect your email account
5. Note down your **SERVICE_ID**

## Step 3: Create Email Template
1. Go to **Email Templates**
2. Click **Create New Template**
3. Set up your template with these variables:
   - `{{from_name}}` - User's name
   - `{{from_email}}` - User's email
   - `{{phone}}` - User's phone number
   - `{{service_interest}}` - Selected service
   - `{{message}}` - User's message

### Example Template:
```
Subject: New Contact Form Submission from {{from_name}}

You have received a new message from your website:

Name: {{from_name}}
Email: {{from_email}}
Phone: {{phone}}
Service Interest: {{service_interest}}

Message:
{{message}}
```

4. Set the **To Email** field to: `info@transitionslegacy.com`
5. Save the template and note down your **TEMPLATE_ID**

## Step 4: Get Your Public Key
1. Go to **Account** in the EmailJS dashboard
2. Find your **Public Key** (also called User ID)
3. Copy it

## Step 5: Update Your Code
Open `js/script.js` and replace these three values:

1. Line with `emailjs.init('YOUR_PUBLIC_KEY');`
   - Replace `YOUR_PUBLIC_KEY` with your actual public key

2. Line with `emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)`
   - Replace `YOUR_SERVICE_ID` with your service ID
   - Replace `YOUR_TEMPLATE_ID` with your template ID

## Example:
```javascript
// Replace this:
emailjs.init('YOUR_PUBLIC_KEY');

// With something like:
emailjs.init('abc123XYZ');

// Replace this:
emailjs.send('YOUR_SERVICE_ID', 'YOUR_TEMPLATE_ID', templateParams)

// With something like:
emailjs.send('service_abc123', 'template_xyz789', templateParams)
```

## Step 6: Test It!
1. Open your website
2. Fill out the contact form
3. Click "Send Message"
4. Check for the email

## Troubleshooting
- Make sure all three IDs are correctly replaced in the code
- Check the browser console for any error messages
- Verify your EmailJS account is active and the service is connected
- Check your spam folder if emails aren't arriving

## Free Tier Limits
- 200 emails per month
- No credit card required
- Perfect for small to medium websites
